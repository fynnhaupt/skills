# Good and bad tests

## Good

Test observable behaviour through the public interface:

```typescript
test('user can checkout with valid cart', async () => {
  const cart = createCart();
  cart.add(product);
  const result = await checkout(cart, paymentMethod);
  expect(result.status).toBe('confirmed');
});
```

- Checks behaviour a caller cares about, through the public interface only.
- Survives refactors that keep the behaviour.
- Its name says what, not how.
- One logical assertion.

## Bad

**Implementation-coupled**: breaks on a refactor although behaviour is unchanged. Tells: mocks internal collaborators, tests private methods, asserts call counts or order.

```typescript
// Bad: tests how, not what
test('checkout calls paymentService.process', async () => {
  const mockPayment = jest.mock(paymentService);
  await checkout(cart, payment);
  expect(mockPayment.process).toHaveBeenCalledWith(cart.total);
});
```

**Side channel**: verifies by reaching past the interface.

```typescript
// Bad: queries the database directly
test('createUser saves to database', async () => {
  await createUser({ name: 'Alice' });
  const row = await db.query('SELECT * FROM users WHERE name = ?', ['Alice']);
  expect(row).toBeDefined();
});

// Good: verifies through the interface
test('createUser makes user retrievable', async () => {
  const user = await createUser({ name: 'Alice' });
  expect((await getUser(user.id)).name).toBe('Alice');
});
```

**Tautological**: the expected value is computed the way the code computes it, so the test passes by construction. Take expected values from an independent source: a literal, a worked example, the spec.

```typescript
// Bad: recomputes the result
const expected = items.reduce((sum, i) => sum + i.price, 0);
expect(calculateTotal(items)).toBe(expected);

// Good: a known literal
expect(calculateTotal([{ price: 10 }, { price: 5 }])).toBe(15);
```
