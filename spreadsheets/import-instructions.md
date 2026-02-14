# CSV Import Instructions for Google Sheets

**Purpose**: Import all 16 CSV deadline tracking files into a single Google Sheets workbook with multiple tabs
**Time Required**: 15-20 minutes
**Last Updated**: February 14, 2026

---

## Overview

This guide will help you create a comprehensive college admissions deadline tracking spreadsheet in Google Sheets by importing 16 CSV files:

- **8 University Tabs**: NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill
- **7 Career Interest Tabs**: Business, Industrial Design, Architecture, Art, Music Production, Film Production, Aerospace Engineering
- **1 Master Timeline Tab**: All deadlines in chronological order

**Result**: A single Google Sheets workbook with 16 tabs for tracking all deadlines and tasks.

---

## Step 1: Create a New Google Sheets Workbook

1. Go to [Google Sheets](https://sheets.google.com)
2. Click **+ Blank** to create a new spreadsheet
3. Name your spreadsheet: **"College Admissions Tracker 2026-2027"**
4. Click **File → Rename** to change the name

---

## Step 2: Import the Master Timeline (First Tab)

**Start with the master timeline to create the structure**

1. In your new Google Sheet, click **File → Import**
2. Click **Upload** tab
3. Click **Browse** and select `master-timeline.csv` from your computer
4. In the **Import location** dropdown, select **Replace current sheet**
5. In the **Separator type** dropdown, select **Comma**
6. Click **Import data**
7. Rename the tab from "Sheet1" to **"Master Timeline"**
   - Right-click on the tab at the bottom
   - Select **Rename**
   - Type "Master Timeline"

---

## Step 3: Import University Tabs (8 Files)

**Repeat these steps for each of the 8 university CSV files**

### University Files to Import:
1. `nc-state.csv` → Tab name: **"NC State"**
2. `duke.csv` → Tab name: **"Duke"**
3. `ucla.csv` → Tab name: **"UCLA"**
4. `app-state.csv` → Tab name: **"App State"**
5. `nc-at.csv` → Tab name: **"NC A&T"**
6. `georgia-tech.csv` → Tab name: **"Georgia Tech"**
7. `unc-charlotte.csv` → Tab name: **"UNC Charlotte"**
8. `unc-chapel-hill.csv` → Tab name: **"UNC Chapel Hill"**

### Import Process for Each File:

1. Click the **+** button at the bottom left to add a new sheet
2. Click **File → Import**
3. Click **Upload** tab
4. Click **Browse** and select the CSV file (e.g., `nc-state.csv`)
5. In the **Import location** dropdown, select **Insert new sheet(s)**
6. In the **Separator type** dropdown, select **Comma**
7. Click **Import data**
8. Rename the new tab to match the university name (e.g., "NC State")
9. Repeat for all 8 university files

---

## Step 4: Import Career Interest Tabs (7 Files)

**Repeat these steps for each of the 7 career CSV files**

### Career Files to Import:
1. `business.csv` → Tab name: **"Business"**
2. `industrial-design.csv` → Tab name: **"Industrial Design"**
3. `architecture.csv` → Tab name: **"Architecture"**
4. `art.csv` → Tab name: **"Art"**
5. `music-production.csv` → Tab name: **"Music Production"**
6. `film-production.csv` → Tab name: **"Film Production"**
7. `aerospace-engineering.csv` → Tab name: **"Aerospace Engineering"**

### Import Process for Each File:

1. Click the **+** button at the bottom left to add a new sheet
2. Click **File → Import**
3. Click **Upload** tab
4. Click **Browse** and select the CSV file (e.g., `business.csv`)
5. In the **Import location** dropdown, select **Insert new sheet(s)**
6. In the **Separator type** dropdown, select **Comma**
7. Click **Import data**
8. Rename the new tab to match the career name (e.g., "Business")
9. Repeat for all 7 career files

---

## Step 5: Organize Your Tabs

**Arrange tabs in a logical order for easy navigation**

### Recommended Tab Order:

1. **Master Timeline** (overview)
2. **NC State** (in-state, primary choice)
3. **Duke** (in-state, highly selective)
4. **UNC Chapel Hill** (in-state, selective)
5. **UNC Charlotte** (in-state)
6. **App State** (in-state)
7. **NC A&T** (in-state)
8. **Georgia Tech** (out-of-state, engineering focus)
9. **UCLA** (out-of-state)
10. **Business** (career interest)
11. **Aerospace Engineering** (career interest)
12. **Industrial Design** (career interest)
13. **Architecture** (career interest)
14. **Art** (career interest)
15. **Music Production** (career interest)
16. **Film Production** (career interest)

### How to Reorder Tabs:

- Click and drag tabs at the bottom of the screen to rearrange them
- Place Master Timeline first, then universities, then career interests

---

## Step 6: Format Your Spreadsheet

**Make the spreadsheet easier to read and use**

### For Each Tab:

1. **Freeze the Header Row**:
   - Click on row 1 (the header row)
   - Click **View → Freeze → 1 row**
   - This keeps column headers visible when scrolling

2. **Bold the Header Row**:
   - Select row 1
   - Click the **Bold** button (or Ctrl+B / Cmd+B)

3. **Adjust Column Widths**:
   - Double-click on the column divider between column letters to auto-fit
   - Or manually drag column dividers to adjust width
   - Recommended widths:
     - Column A (Task/Milestone Name): 350 pixels
     - Column B (Target Date): 120 pixels
     - Column C (Completion Status): 150 pixels
     - Column D (Notes): 300 pixels
     - Column E (Responsible Party): 150 pixels

4. **Center-Align Date and Status Columns**:
   - Select column B (Target Date)
   - Click **Format → Align → Center**
   - Repeat for column C (Completion Status)

---

## Step 7: Add Conditional Formatting (Optional but Recommended)

**Highlight completed tasks and upcoming deadlines**

### Highlight Completed Tasks (Green):

1. Select column C (Completion Status) in any tab
2. Click **Format → Conditional formatting**
3. Under **Format rules**, choose **Text contains**
4. Enter: `Completed` or `Complete`
5. Under **Formatting style**, choose a green background
6. Click **Done**
7. Repeat for each tab

### Highlight Pending Tasks (Yellow):

1. Select column C (Completion Status) in any tab
2. Click **Format → Conditional formatting**
3. Under **Format rules**, choose **Text contains**
4. Enter: `Pending`
5. Under **Formatting style**, choose a yellow background
6. Click **Done**
7. Repeat for each tab

### Highlight Upcoming Deadlines (Red):

1. Select column B (Target Date) in any tab
2. Click **Format → Conditional formatting**
3. Under **Format rules**, choose **Date is before**
4. Choose **Today + 7 days** (for deadlines within 1 week)
5. Under **Formatting style**, choose a red background
6. Click **Done**
7. Repeat for each tab

---

## Step 8: Add Dropdown Menu for Completion Status (Optional)

**Make it easier to update task status**

### For Each Tab:

1. Select column C (Completion Status) starting from row 2 (skip header)
2. Click **Data → Data validation**
3. Under **Criteria**, choose **List of items**
4. Enter: `Pending,In Progress,Completed`
5. Check **Show dropdown list in cell**
6. Check **Reject input** (optional - ensures only valid values)
7. Click **Save**
8. Repeat for each tab

---

## Step 9: Add Formulas for Date-Based Sorting (Advanced - Optional)

**Automatically sort by date or show days remaining**

### Add "Days Until" Column:

1. Insert a new column after column B (Target Date)
2. Name it "Days Until"
3. In cell C2 (first data row), enter formula:
   ```
   =IF(B2="","",B2-TODAY())
   ```
4. Copy this formula down the entire column
5. This shows how many days until each deadline
6. Negative numbers = deadline has passed

### Sort by Date:

1. Select all data in a tab (click cell A1, then Ctrl+Shift+End or Cmd+Shift+End)
2. Click **Data → Create a filter**
3. Click the filter icon in column B (Target Date)
4. Choose **Sort A → Z** to sort oldest to newest

---

## Step 10: Share with Family Members

**Allow parents and student to access and edit the spreadsheet**

1. Click the **Share** button in the top right
2. Enter email addresses for family members
3. Choose **Editor** access (allows editing)
4. Click **Send**
5. Or click **Copy link** and share the link with family

---

## Tips for Using Your Spreadsheet

### Daily/Weekly Tasks:

- **Every Monday**: Review Master Timeline for upcoming week's deadlines
- **Before each deadline**: Check university-specific tab for details
- **After completing a task**: Update "Completion Status" to "Completed"
- **After receiving decisions**: Update notes with acceptance/rejection/waitlist

### Monthly Review:

- **First of each month**: Review all tabs for upcoming deadlines in next 30 days
- **Update dates**: If universities change deadlines, update CSV files and re-import
- **Add notes**: Document progress, questions, or changes in Notes column

### Best Practices:

- **Use Master Timeline** for quick overview of all deadlines
- **Use University Tabs** for detailed requirements and tracking per school
- **Use Career Tabs** for research tasks related to specific programs
- **Keep Notes**: Document when tasks are completed, confirmation numbers, portal logins
- **Backup regularly**: Google Sheets auto-saves, but download a copy monthly as backup

---

## Troubleshooting

### Problem: CSV file won't import

**Solution**:
- Ensure the file is saved as `.csv` format (not `.xlsx` or `.txt`)
- Try opening the CSV in a text editor to verify it's comma-separated
- Re-download the CSV file if it appears corrupted

### Problem: Special characters look wrong (e.g., â€™ instead of ')

**Solution**:
- When importing, select **UTF-8** as the character encoding
- Or re-save the CSV file with UTF-8 encoding in a text editor

### Problem: Dates aren't recognized as dates

**Solution**:
- Select the date column
- Click **Format → Number → Date**
- Ensure dates are in YYYY-MM-DD format in the CSV

### Problem: Too many tabs to navigate easily

**Solution**:
- Use **Tab Colors** to categorize tabs:
  - Right-click tab → Change color
  - Use blue for universities, green for careers, red for master timeline
- Bookmark frequently used tabs by keeping them leftmost

---

## Updating the Spreadsheet with New Information

**When university deadlines change or new tasks are added**

### Option 1: Manual Update (Quick)

1. Open the Google Sheet
2. Navigate to the relevant tab
3. Add/edit/delete rows as needed
4. Update dates or notes directly in the spreadsheet

### Option 2: Re-Import CSV (Recommended for major changes)

1. Update the CSV file on your computer with new information
2. In Google Sheets, click **File → Import**
3. Upload the updated CSV
4. Select **Replace current sheet** for the specific tab
5. Click **Import data**
6. Note: This will overwrite any manual changes you made to that tab

### Option 3: AI-Assisted Update (Monthly)

See the guide's **Section 8: AI Update Guide** for instructions on using Claude or other AI to:
- Check all university websites for deadline changes
- Generate updated CSV files with latest information
- Identify what has changed since last update

---

## Getting Help

- **Google Sheets Help**: https://support.google.com/docs/topic/9054603
- **CSV Formatting Issues**: Open CSV in plain text editor to verify structure
- **College Admissions Questions**: Contact university admissions offices directly

---

**Setup Complete!** You now have a comprehensive deadline tracking system for the student's college admissions journey.

**Next Steps**:
1. Review the Master Timeline to see all upcoming deadlines
2. Check the current month's tasks in the timeline
3. Begin working on the earliest deadline tasks
4. Set up calendar reminders for critical deadlines

**Recommended**: Set up Google Calendar integration to get notifications 1 week before major deadlines.

---

**File Location**: `/spreadsheets/import-instructions.md`
**Related Files**: All 16 CSV files in `/spreadsheets/` directory
**Last Updated**: February 14, 2026
