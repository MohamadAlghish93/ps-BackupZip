# ps-BackupZip

## Description

`ps-BackupZip` is a PowerShell script designed to automate the backup of folders listed in a CSV file to a compressed archive. This script provides functionalities such as reading backup settings from a JSON file, calculating folder sizes, managing log files, and creating ZIP archives of specified folders.

## Features

- **Automated Backups**: Automatically backs up folders listed in a CSV file.
- **Settings Management**: Reads and saves backup settings in a JSON file.
- **Folder Size Calculation**: Calculates the size of folders to be backed up.
- **Log Files Management**: Includes options to include, exclude, or delete log files from the backup.
- **Error Handling**: Handles errors and logs them appropriately.
- **Progress Tracking**: Displays progress and summary of the backup process.

## Prerequisites

- PowerShell 5.0 or later
- CSV file (`Backup-folder.csv`) containing the list of folders to back up
- JSON file (`backup_settings.json`) for storing backup settings (optional)

## Usage

1. **Prepare CSV File**: Create a CSV file named `Backup-folder.csv` in the same directory as the script. The CSV file should have the following structure:

    ```csv
    name,app,LogAction
    Folder1,C:\path\to\folder1,include
    Folder2,C:\path\to\folder2,exclude
    ```

2. **Run the Script**: Execute the script `csv-folder-zip.ps1` in PowerShell.

    ```powershell
    .\csv-folder-zip.ps1
    ```

3. **Follow Prompts**: If backup settings are not found, the script will prompt for the destination folder, log file extensions, and default log action.

4. **Backup Process**: The script will process each folder listed in the CSV file, create ZIP archives, and display a summary of the backup process.

## Script Details

The script performs the following functions:

- **Get-BackupSettings**: Reads backup settings from a JSON file.
- **Save-BackupSettings**: Saves backup settings to a JSON file.
- **Get-FolderSize**: Calculates the size of a folder.
- **Get-LogFilesInfo**: Retrieves information about log files in a folder.
- **New-BackupArchive**: Creates a ZIP archive of a folder.
- **Start-BackupProcess**: Main function that orchestrates the backup process.

## Example

An example CSV file (`Backup-folder.csv`):

```csv
name,app,LogAction
ProjectA,C:\Projects\ProjectA,include
ProjectB,C:\Projects\ProjectB,exclude
```

An example JSON settings file (`backup_settings.json`):

```json
{
    "DestinationFolder": "C:\\Backups",
    "LogExtensions": ["*.log", "*.txt"],
    "DefaultLogAction": "include"
}
```

## License

This project is licensed under the MIT License.
