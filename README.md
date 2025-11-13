Soroban Performance Benchmarks
A comprehensive performance tracking tool for Soroban smart contracts built with React and Recharts.
📋 Table of Contents

Overview
Features
Installation
Usage
Metrics Tracked
Performance Thresholds
Component Structure
Customization

🎯 Overview
This interactive dashboard helps developers monitor and analyze the performance of Soroban smart contract functions. Track gas consumption, execution time, storage operations, and identify performance bottlenecks in real-time.
✨ Features

Real-time Metrics Dashboard - Visual overview of average gas usage, execution time, and storage operations
Interactive Charts - Bar and line charts for gas usage and execution time comparison
Add Custom Benchmarks - Manually input benchmark data for any contract function
Benchmark History - Complete historical record with color-coded performance indicators
Performance Thresholds - Automatic status indicators (Optimal/Warning/Critical)
Responsive Design - Works seamlessly on desktop and mobile devices

🚀 Installation
Prerequisites

Node.js 14+
npm or yarn

Setup

Install dependencies:

bashnpm install react recharts lucide-react

Copy the component to your project:

bash# Save the component as SorobanBenchmarks.jsx

Import and use in your app:

jsximport SorobanBenchmarks from './SorobanBenchmarks';

function App() {
  return <SorobanBenchmarks />;
}
📊 Usage
Viewing Metrics
Navigate to the Metrics Overview tab to see:

Average gas consumption across all functions
Average execution time
Total storage operations
Visual charts comparing function performance

Adding Benchmarks

Click the Add Benchmark tab
Fill in the form:

Function Name: Name of the smart contract function (e.g., create_pass)
Gas Used: Gas consumption in units
Execution Time: Time in milliseconds
Storage Operations: Number of storage reads/writes


Click Add Benchmark

Viewing History
The Benchmark History tab shows all recorded benchmarks with:

Color-coded performance indicators
Sortable columns
Delete functionality for individual records

📈 Metrics Tracked
MetricDescriptionUnitGas UsedTotal gas consumed by the functionGas unitsExecution TimeTime taken to execute the functionMilliseconds (ms)Storage OperationsNumber of read/write operationsCountSuccess StatusWhether the function executed successfullyBoolean
⚡ Performance Thresholds
Gas Usage

🟢 Optimal: < 100,000 units
🟡 Warning: 100,000 - 150,000 units
🔴 Critical: > 150,000 units

Execution Time

🟢 Optimal: < 200ms
🟡 Warning: 200ms - 300ms
🔴 Critical: > 300ms

🏗️ Component Structure
SorobanBenchmarks/
├── State Management
│   ├── activeTab - Current tab selection
│   ├── benchmarks - Array of benchmark records
│   └── newBenchmark - Form input state
│
├── Tabs
│   ├── Metrics Overview - Dashboard with charts
│   ├── Add Benchmark - Input form
│   └── Benchmark History - Data table
│
└── Functions
    ├── addBenchmark() - Add new record
    ├── deleteBenchmark() - Remove record
    └── getStatusColor() - Color coding logic
🎨 Customization
Adjusting Thresholds
Edit the performanceThresholds object:
javascriptconst performanceThresholds = {
  gas: { 
    optimal: 100000,   // Change these values
    warning: 150000, 
    critical: 200000 
  },
  time: { 
    optimal: 200,      // Change these values
    warning: 300, 
    critical: 500 
  }
};
Styling
The component uses Tailwind CSS. Customize colors by modifying className properties:
javascript// Example: Change primary color from blue to purple
className="bg-blue-600" // Change to
className="bg-purple-600"
Adding New Metrics

Add new field to benchmark state:

javascriptconst [benchmarks, setBenchmarks] = useState([{
  // ... existing fields
  yourNewMetric: 0  // Add here
}]);

Update the form in "Add Benchmark" tab
Display in the history table

💡 Best Practices

Consistent Testing Environment: Run benchmarks in the same environment for accurate comparisons
Multiple Runs: Test each function multiple times and record averages
Monitor Trends: Look for performance degradation over time
Set Realistic Thresholds: Adjust thresholds based on your specific use case

🔧 Troubleshooting
Charts not displaying?

Ensure recharts is properly installed: npm install recharts

Data not persisting?

This component uses in-memory state. For persistence, integrate with a backend or localStorage

Icons missing?

Install lucide-react: npm install lucide-react

📝 License
MIT License - feel free to use in your projects!
🤝 Contributing
Contributions welcome! Feel free to:

Report bugs
Suggest new features
Submit pull requests

📞 Support
For issues or questions, please open an issue in the repository or contact the development team.

Built with ❤️ for the Soroban developer community
