# Mocking

Mock only at **system boundaries**: external APIs, time, randomness, and sometimes the database or file system (prefer a test database). Never mock your own modules or anything else you control.

Make boundaries easy to mock:

- **Pass dependencies in** instead of creating them inside:

  ```typescript
  // Easy to mock
  function processPayment(order, paymentClient) {
    return paymentClient.charge(order.total);
  }
  ```

- **One function per external operation** instead of a generic fetcher, so each mock returns one shape and needs no branching:

  ```typescript
  const api = {
    getUser: (id) => fetch(`/users/${id}`),
    createOrder: (data) => fetch('/orders', { method: 'POST', body: data })
  };
  ```
