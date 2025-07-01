# Library Management System - Windows Forms Application

A comprehensive C# .NET WinForms application for managing library resources with custom data structures and efficient search algorithms.

## Features

### Core Functionality
- **Resource Management**: Add, edit, delete library resources (books, journals, media)
- **Search Capabilities**: Multiple search algorithms with different time complexities
- **Borrowing System**: Track borrowed items and due dates
- **Reports**: Generate overdue reports and resource statistics

### Technical Implementation
- **Custom Data Structures**: Hash table and binary search tree implementations
- **Database Integration**: Entity Framework Core with SQL Server
- **Time Complexity Optimization**: O(1) hash table lookups, O(log n) BST searches
- **Windows Forms UI**: Clean, intuitive desktop interface

## Architecture

### Data Structures
1. **Custom Hash Table**: O(1) average case search for ID and genre lookups
2. **Binary Search Tree**: O(log n) search for title and author with prefix matching
3. **Entity Framework Models**: Database persistence layer

### Search Algorithms
1. **Hash Table Search**: Constant time lookup for exact matches
2. **BST Prefix Search**: Logarithmic time search with prefix matching capability

## Time Complexity Analysis

| Operation | Hash Table | Binary Search Tree |
|-----------|------------|-------------------|
| Insert | O(1) avg | O(log n) avg |
| Search | O(1) avg | O(log n) avg |
| Delete | O(1) avg | O(log n) avg |
| Prefix Search | N/A | O(n) |

## Setup Instructions

### Prerequisites
- .NET 6.0 or later
- SQL Server LocalDB
- Visual Studio 2022 (recommended)

### Installation
1. Download and extract the project files
2. Open `LibraryManagementSystem.sln` in Visual Studio
3. Restore NuGet packages (Build → Restore NuGet Packages)
4. Update connection string in `Data/LibraryContext.cs` if needed
5. Run the database creation script from `Database/CreateDatabase.sql`
6. Build and run the application (F5)

### Database Setup
Run these SQL scripts in SQL Server Management Studio or Visual Studio:
1. `Database/CreateDatabase.sql` (required)
2. `Database/SeedData.sql` (optional, for sample data)

## Usage

### Main Features
1. **Add Resources**: Click "Add Resource" to add new books, journals, or media
2. **Search**: Use the search box with different criteria (Title, Author, Genre)
3. **Borrow/Return**: Select a resource and use Borrow/Return buttons
4. **Reports**: View overdue items and resource statistics

### Search Types
- **Title Search**: Uses BST for efficient prefix matching
- **Author Search**: Uses BST for efficient prefix matching  
- **Genre Search**: Uses hash table for instant lookup
- **ID Search**: Uses hash table for instant lookup

## Project Structure

\`\`\`
LibraryManagementSystem/
├── Models/
│   └── LibraryResource.cs          # Data model and enums
├── Data/
│   └── LibraryContext.cs           # Entity Framework context
├── DataStructures/
│   ├── CustomHashTable.cs         # Custom hash table implementation
│   └── BinarySearchTree.cs        # Custom BST implementation
├── Services/
│   └── LibraryService.cs           # Business logic layer
├── Forms/
│   ├── MainForm.cs                 # Main application window
│   ├── ResourceForm.cs             # Add/Edit resource dialog
│   ├── BorrowForm.cs               # Borrow resource dialog
│   └── ReportsForm.cs              # Reports window
├── Database/
│   ├── CreateDatabase.sql          # Database creation script
│   └── SeedData.sql                # Sample data script
├── Program.cs                      # Application entry point
└── LibraryManagementSystem.csproj  # Project file
\`\`\`

## Performance Characteristics

### Scalability
- Efficient for up to 10,000+ resources
- Hash table provides O(1) lookups
- BST provides sorted access and range queries
- Database indexes optimize SQL queries

### Memory Usage
- O(n) space complexity for each index
- Total memory: O(4n) for all indexes combined
- Efficient memory management with proper disposal

## Key Features

1. **Custom Data Structures**: Implemented from scratch for educational purposes
2. **Efficient Search**: Multiple algorithms optimized for different use cases
3. **Database Integration**: Full CRUD operations with Entity Framework
4. **User-Friendly Interface**: Intuitive Windows Forms design
5. **Comprehensive Reports**: Overdue tracking and statistics

## Troubleshooting

### Common Issues
1. **Database Connection**: Ensure SQL Server LocalDB is installed
2. **Missing References**: Restore NuGet packages in Visual Studio
3. **Build Errors**: Check .NET 6.0 SDK is installed

### Database Issues
- If database creation fails, check SQL Server LocalDB service is running
- Update connection string in `LibraryContext.cs` for different SQL Server instances

## Future Enhancements

1. **Self-Balancing Trees**: Implement AVL or Red-Black trees for guaranteed O(log n)
2. **Advanced Search**: Add full-text search capabilities
3. **User Management**: Add authentication and role-based access
4. **Backup/Restore**: Implement data backup functionality
5. **Barcode Integration**: Add barcode scanning support

## License

This project is for educational purposes and demonstrates advanced data structures and algorithms in a practical Windows Forms application.
