# Kanban Application - Playwright Automation Test Suite

A comprehensive end-to-end test automation suite for a Kanban web application, built with Playwright and designed to handle dynamic data scenarios.

## 📋 Overview

This project contains automated tests for a Kanban board application hosted at [https://kanban-566d8.firebaseapp.com](https://kanban-566d8.firebaseapp.com). The tests are designed to work reliably even when the application data changes on each page refresh.

## 🎯 Test Cases Covered

### Test Case 1: Edit Kanban Card ✅
**Objective**: Edit a Kanban card to mark a subtask as complete and move the card to the first column.

**Steps:**
1. Navigate to the Kanban app
2. Choose a card with incomplete subtasks not in the first column
3. Complete one subtask
4. Move task to the first column via Current Status dropdown
5. Verify that the subtask is striked through
6. Close the card edit page
7. Verify that the number of completed subtasks is correct
8. Verify that the card moved to the correct column

## 🛠️ Technologies Used

- **Playwright** - End-to-end testing framework
- **JavaScript** - Test implementation language
- **Node.js** - Runtime environment

## 📦 Installation

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd kanban-automation-test
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Install Playwright browsers**
   ```bash
   npx playwright install
   ```

## 🚀 Running Tests

### Run all tests once
```bash
npx playwright test
```

### Run tests with 5 repetitions (as per requirements)
```bash
npx playwright test --repeat-each 5
```

### Run tests in headed mode (see browser)
```bash
npx playwright test --headed
```


### View test report
```bash
npx playwright show-report
```

## 📊 Test Reports

After running tests, an HTML report is automatically generated in the `playwright-report/` directory. The report includes:
- Test execution results
- Screenshots on failure
- Video recordings on failure
- Detailed step-by-step logs
- Performance metrics

## 🏗️ Project Structure

```
kanban-automation-test/
├── tests/
│   └── kanban.spec.js          # Main test file with all test cases
├── playwright-report/           # Generated HTML reports
├── test-results/                # Test execution artifacts
├── playwright.config.js         # Playwright configuration
├── package.json                 # Project dependencies
└── README.md                    # This file
```

## ⚙️ Configuration

The `playwright.config.js` file contains:
- Base URL configuration
- Browser settings (Chromium)
- Timeout settings
- Screenshot and video capture options
- HTML report configuration

Key settings:
```javascript
baseURL: 'https://kanban-566d8.firebaseapp.com'
timeout: 60000  // 1 minute per test
globalTimeout: 600000  // 10 minutes total
```

## 🎨 Key Features

### Robust Test Design
- ✅ Handles dynamic data that changes on page refresh
- ✅ Works with varying column names and card contents
- ✅ Smart element selection using multiple fallback strategies
- ✅ Comprehensive error handling and logging

### Dynamic Selectors
- Uses content-based selectors rather than fixed indices
- Adapts to changing column names and card titles
- Finds elements by their characteristics (e.g., cards with incomplete subtasks)

### Verification Strategy
- Validates subtask completion count changes
- Verifies card movement between columns
- Confirms strikethrough styling on completed subtasks
- Checks card deletion and count updates

## 📈 Test Metrics

Current test performance:
- **Success Rate**: 100% (5/5 runs)
- **Average Execution Time**: ~6-8 seconds per test
- **Steps Covered**: 7/7 for Test Case 1, 4/4 for Test Case 2

## 🐛 Troubleshooting

### Tests failing intermittently?
- Increase timeout values in `playwright.config.js`
- Check network connectivity to the Kanban app
- Verify the application is accessible and responsive

### Elements not found?
- The test includes extensive logging - check console output
- Screenshots and videos are captured on failure
- Review the HTML report for detailed execution steps

### Browser issues?
```bash
# Reinstall browsers
npx playwright install --force
```

## 📝 Development Notes

### Design Principles
1. **Adaptability**: Tests work with any data configuration
2. **Reliability**: Multiple fallback strategies for element selection
3. **Maintainability**: Clear logging and descriptive variable names
4. **Completeness**: Comprehensive assertions for all requirements

### Best Practices Implemented
- Wait for network idle before interactions
- Use meaningful timeout values
- Implement retry logic for flaky operations
- Clear console logging for debugging
- Proper test isolation (each test is independent)


This project is part of a technical assessment for Checksum.

---

**Note**: This automation suite is designed specifically for the Kanban application at https://kanban-566d8.firebaseapp.com and may need adjustments for other Kanban implementations.
