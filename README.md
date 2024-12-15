# Project Title: Jest CI with GitHub Actions

## Overview
This project demonstrates how to set up Continuous Integration (CI) for a JavaScript project using Jest for testing and GitHub Actions for automated workflows.

---

## 📋 Steps to Set Up CI with Jest and GitHub Actions

### 1. **Initialize the Project**

1. Create a new Node.js project:
   ```bash
   npm init -y
   ```

2. Install Jest as a development dependency:
   ```bash
   npm install jest --save-dev
   ```

3. Add the following test script to `package.json`:
   ```json
   "scripts": {
     "test": "jest"
   }
   ```

### 2. **Write a Sample Test**

Create a test file in `__tests__/example.test.js`:

```javascript
test('adds 1 + 2 to equal 3', () => {
  expect(1 + 2).toBe(3);
});
```

### 3. **Run Tests Locally**

Execute the tests with:

```bash
npx jest
```

### 4. **Set Up GitHub Actions Workflow**

Create a GitHub Actions workflow file at `.github/workflows/ci.yml` with the following content:

```yaml
name: Jest CI

on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Setup Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '16'
      - run: npm install
      - run: npm test
```

### 5. **Push the Workflow to GitHub**

```bash
git add .
git commit -m "Add CI workflow"
git push -u origin main
```

---

## 🛠️ Workflow Execution

Once you push the changes, GitHub Actions will run the tests automatically.

### 🔹 **Workflow in GitHub Actions**

![GitHub Actions Workflow](path/to/your-actions-workflow-screenshot.png)

### 🔹 **Console Test Results**

![Console Test Results](path/to/your-console-test-results-screenshot.png)

---

## ✅ Conclusion

This setup ensures that all changes pushed to the `main` branch are automatically tested, helping maintain code quality and reliability.

---

## 🚀 Future Improvements

- Add more tests for additional functionality.
- Integrate notifications (e.g., Slack or email) for build status.

---

## 📎 Resources

- [Jest Documentation](https://jestjs.io/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
