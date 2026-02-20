# 📚 NESA Course Mapping Tool

A web-based tool that automates the mapping of student class enrolments from Sentral to NESA course codes for upload to Schools Online.

## 🌐 Live Demo

**[Launch the Tool](https://kiatinw.github.io/nesa-mapping-tool/)**

---

## 🎯 What Does This Tool Do?

This tool streamlines the tedious process of mapping student timetable data from Sentral to NESA-compliant course codes. Instead of manually matching hundreds of students and dozens of class codes, this tool:

1. **Automatically matches students** from Sentral to NESA records based on names
2. **Auto-maps class codes** to NESA course numbers using an intelligent matching system
3. **Generates a ready-to-upload CSV** with all the data Schools Online requires
4. **Highlights issues** like unmatched students or unmapped classes for manual review

**Time saved:** What used to take hours now takes minutes! ⏱️

---

## ✨ Features

### 🤖 Automatic Matching
- **Student Matching**: Automatically pairs Sentral students with NESA records by name
- **Class Mapping**: Recognizes 60+ subject codes (MMA, SPH, HBS, etc.) and maps them to NESA courses
- **Smart Year Detection**: Handles Year 10 vs Year 11 differences (e.g., 200-hour courses vs Preliminary courses)

### 👁️ Manual Control
- **Review Interface**: See all automatic matches before confirming
- **Manual Override**: Easily fix incorrect matches with dropdown menus
- **Delete Classes**: Remove non-academic classes (study periods, home room, etc.)
- **Custom Course Codes**: Enter course codes manually for Board Endorsed Courses

### 📊 Quality Assurance
- **Color-Coded Feedback**: Green = mapped, Orange = needs attention, Red = deleted
- **Warning Lists**: See all unmatched students and unmapped classes before finalizing
- **Verification Columns**: Output includes Sentral data alongside NESA data for double-checking

### 🔒 Privacy & Security
- **100% Client-Side**: All processing happens in your browser
- **No Data Upload**: Your student data never leaves your computer
- **No Server**: Everything runs locally - no external servers involved

---

## 🚀 How to Use

### Step 1: Prepare Your Files

You need **three files**:

#### 📄 Student Attendance Spreadsheet (from Sentral)
1. Go to **Profiles** → **Exports**
2. Select your year level
3. Export settings should match the screenshot provided in the tool
4. Download as `.xls` or `.xlsx`
5. **Do not modify** the file after downloading

#### 📄 NESA Course Codes (from Schools Online)
1. Go to **Courses Offered at Your School**
2. Select the correct year of study
3. Check **"Show only courses offered"**
4. Download the `.csv` file
5. **Do not modify** the file

#### 📄 NESA Student Template (from Schools Online)
1. Go to **20XX Enrolments**
2. Select **"Load Student Courses from a file"**
3. Click **"create entry file"** on the left
4. Download the `.csv` file
5. **Do not modify** the file

### Step 2: Upload to Tool

1. **Upload Student Attendance** → The tool extracts unique class codes
2. **Upload NESA Course Codes** → The tool loads available courses
3. **Upload NESA Template** → The tool automatically matches students

### Step 3: Review Matches

- ✅ **Green (Matched)**: Student automatically matched - verify it looks correct
- ⚠️ **Orange (Unmatched)**: Use the dropdown to manually select the correct NESA student
- 💡 **Tip**: Use "Hide Matched Students" button to focus on students needing attention

### Step 4: Map Classes

1. Select **Year 10** or **Year 11**
2. Review the automatic class mappings (most should be correct!)
3. Manually map any classes that weren't auto-matched
4. Check the **Delete** box for classes you don't want in the output
5. Use the text box to manually enter course codes if needed

### Step 5: Download & Finalize

1. Click **"Generate Output Spreadsheet"**
2. Review the warning lists (unmatched students, unmapped classes)
3. Open the downloaded CSV file
4. **Delete students without NESA IDs** (if any)
5. **Delete columns C, D, and E** (verification columns)
6. **Final check** for any remaining class codes instead of course numbers
7. **Upload to Schools Online** ✅

---

## 🎓 Subject Codes Supported

The tool recognizes these faculty prefixes and subject codes:

### Mathematics (M)
- `MMA` - Mathematics Advanced
- `MMS` - Mathematics Standard
- `MMX` - Mathematics Extension (Year 11)
- `MXX` - Mathematics Extension 2

### English (E)
- `ENA` - English Advanced
- `ENS` - English Standard
- `ENX` - English Extension (Year 11)
- `EXX` - English Extension 2
- `EDR` - Drama
- `ESL` - English as a Second Language

### Science (S)
- `SPH` - Physics
- `SCH` - Chemistry
- `SBI` - Biology
- `SEE` - Earth & Environmental Science
- `SIS` - Investigating Science

### HSIE (H)
- `HBS` - Business Studies
- `HLS` - Legal Studies
- `HAH` - Ancient History
- `HMH` - Modern History
- `HGE` - Geography
- `HEC` - Economics
- `HSC` - Society and Culture

### CAPA (C)
- `CVA` - Visual Arts
- `CMU` - Music
- `CDA` - Dance
- `CDR` - Drama

### TAS (T)
- `TDT` - Design and Technology
- `TFT` - Food Technology
- `TIT` - Industrial Technology
- `TTD` - Textiles and Design
- `TSW` - Software Design
- `TIM` - Information Processes & Technology
- `TES` - Engineering Studies

### PDHPE (P)
- `PPE` - Personal Development, Health and Physical Education
- `PSP` - Sport, Lifestyle and Recreation

### Languages (L)
- `LFR` - French
- `LSP` - Spanish
- `LGE` - German
- `LJP` - Japanese
- `LCH` - Chinese
- `LIT` - Italian
- `LLA` - Latin

**...and more!** Over 60 subject codes in total.

---

## ⚙️ Technical Details

### Built With
- **Vanilla JavaScript** - No frameworks, just pure JS
- **SheetJS (xlsx.js)** - Excel file processing
- **PapaParse** - CSV parsing
- **HTML5 & CSS3** - Modern, responsive design

### Browser Compatibility
- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ⚠️ Internet Explorer NOT supported

### File Formats
- **Input**: `.xls`, `.xlsx`, `.csv`
- **Output**: `.csv` (ready for Schools Online)

---

## 🐛 Troubleshooting

### Files Won't Upload
- ✅ Check file format (`.xls`/`.xlsx` for Sentral, `.csv` for NESA files)
- ✅ Don't modify files after downloading
- ✅ Try refreshing the page
- ✅ Check browser console (F12) for errors

### Students Not Matching
- Names are spelled differently (e.g., "Jon" vs "John")
- Student uses a nickname in one system
- Student is new and not in NESA records yet
- **Solution**: Use the dropdown to manually match

### Classes Not Auto-Mapping
- Subject code not in the database (60+ codes supported)
- School uses different naming convention
- Board Endorsed Course or VET subject
- **Solution**: Use dropdown or text box to manually map

### Schools Online Rejects File
- ❌ Students without NESA IDs still in file → Delete them!
- ❌ Columns C, D, E not deleted → Delete them!
- ❌ File saved as `.xlsx` instead of `.csv` → Re-save as CSV
- ❌ Class codes still present instead of course numbers → Map them!

---

## 📖 FAQ

**Q: Is my student data safe?**  
A: Yes! Everything runs in your browser. No data is sent to any server.

**Q: Can I use this for Year 12?**  
A: The tool is designed for Year 10 and 11. Year 12 mapping may work but hasn't been tested.

**Q: What if my school uses different class codes?**  
A: Use the manual text box to enter course codes, or contact the developer to add your codes.

**Q: Can I save my work and come back later?**  
A: No, the tool doesn't save state. Complete the mapping in one session.

**Q: How do I add more subject codes?**  
A: You can edit the `index.html` file and add codes to the `mappingHints` object around line 1100.

---

## 🔄 Updates & Versioning

The footer of the tool shows the last commit date/time automatically via GitHub API. Version history:

- **v1.0** (February 2025) - Initial release
  - Student matching
  - Class auto-mapping
  - Year 10/11 support
  - 60+ subject codes

---

## 🤝 Contributing

Found a bug? Have a subject code to add? Suggestions for improvement?

1. Check the [FAQ page](https://kiatinw.github.io/nesa-mapping-tool/faq.html) first
2. Open an issue on GitHub
3. Or submit a pull request!

---

## 📜 License

This tool is provided free for educational use. Created to save teachers time on administrative tasks.

---

## 🙏 Acknowledgments

- Built for NSW teachers dealing with NESA reporting
- Inspired by the need to automate tedious manual data entry
- Thanks to all the teachers who provided feedback during development

---

## 📞 Support

- **Documentation**: See the [FAQ page](https://kiatinw.github.io/nesa-mapping-tool/faq.html)
- **Issues**: Open a GitHub issue
- **Questions**: Check the built-in Help & FAQs button in the tool

---

## ⚠️ Disclaimer

This tool is provided as-is. While every effort has been made to ensure accuracy, **always review the output before uploading to Schools Online**. The verification columns (C, D, E) are included specifically for double-checking matches.

---

**Made with ❤️ for NSW Teachers**

*Last updated: February 2025*
