# 📄 Layout Documentation: `activity_main.xml`

## File Summary
- **File Name**: `activity_main.xml`
- **Path**: `app/src/main/res/layout/activity_main.xml`
- **Purpose**: Defines the Homepage UI for the Learning Contract application.
- **Root Element**: `ScrollView`
- **Primary Layout Container**: Vertical `LinearLayout`
- **UI Card Containers**: 6 `androidx.cardview.widget.CardView` elements

---

## 1. Architectural View Hierarchy

```text
ScrollView (Vertical Scroll Container)
└── LinearLayout (orientation="vertical")
    ├── CardView #1 (Title Section)
    │   └── LinearLayout
    │       ├── TextView (tvContractTitle: "Learning Contract")
    │       ├── TextView (tvGroupInfo: "Groupwork # 1")
    │       └── TextView (tvCourseInfo: "Course: Mobile App Development...")
    ├── CardView #2 (Expectations)
    │   └── LinearLayout
    │       ├── TextView ("Expectations")
    │       └── TextView (Bullet points: Kotlin, App Prototype, Gradle Sync)
    ├── CardView #3 (Contributions)
    │   └── LinearLayout
    │       ├── TextView ("Contributions")
    │       └── TextView (Bullet points: UI design, standups, debugging)
    ├── CardView #4 (Motivations)
    │   └── LinearLayout
    │       ├── TextView ("Motivations")
    │       └── TextView (Bullet points: Problem solving, career, portfolio)
    ├── CardView #5 (Hindrance & Mitigations)
    │   └── LinearLayout
    │       ├── TextView ("Hindrance & Mitigations")
    │       └── TextView (Challenges: Time management, syntax learning)
    └── CardView #6 (Signed By)
        └── LinearLayout
            ├── TextView ("Signed By")
            ├── TextView (Student Group: UniSync Members)
            ├── TextView (Instructor Signature: Sir Venn Edward Nicolas)
            └── TextView (Date Signed: October 1, 2026)
```

---

## 2. Detailed Breakdown of XML Components & Attributes

### A. Document Header & Namespaces
```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F8F9FA"
    android:padding="16dp">
```

- **`<?xml version="1.0" encoding="utf-8"?>`**: Standard XML declaration using UTF-8 character encoding.
- **`xmlns:android`**: Declares the core Android framework XML namespace.
- **`xmlns:app`**: Declares custom app/library attributes (used for CardView parameters like `app:cardCornerRadius`).
- **`android:layout_width="match_parent"`**: Expands the ScrollView to cover the full width of the phone display.
- **`android:layout_height="match_parent"`**: Expands the ScrollView to cover the full height of the display window.
- **`android:background="#F8F9FA"`**: Sets a soft light-gray background color.
- **`android:padding="16dp"`**: Adds `16dp` inner padding around all edges of the screen.

---

### B. Vertical Parent Layout
```xml
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical">
```

- **`android:orientation="vertical"`**: Forces all 6 CardView children to stack sequentially from top to bottom.
- **`android:layout_height="wrap_content"`**: Height dynamically adapts to fit all child cards inside the ScrollView.

---

### C. CardView Container Specification (`androidx.cardview.widget.CardView`)
```xml
<androidx.cardview.widget.CardView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_marginBottom="16dp"
    app:cardCornerRadius="12dp"
    app:cardElevation="2dp">
```

| Attribute | Value | Explanation |
| :--- | :--- | :--- |
| `android:layout_width` | `"match_parent"` | Card spans across the full width of the parent layout. |
| `android:layout_height` | `"wrap_content"` | Card height adjusts to the text contained inside it. |
| `android:layout_marginBottom` | `"16dp"` | Separates each section card with `16dp` vertical space. |
| `app:cardCornerRadius` | `"12dp"` | Applies rounded corners (`12dp` radius) to card borders. |
| `app:cardElevation` | `"2dp"` | Adds a subtle `2dp` drop-shadow under the card for elevation. |

---

### D. Inner Text View Attributes (`TextView`)

```xml
<TextView
    android:id="@+id/tvContractTitle"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Learning Contract"
    android:textSize="22sp"
    android:textStyle="bold"
    android:textColor="#1E1B18" />
```

| Attribute | Purpose & Technical Explanation |
| :--- | :--- |
| `android:id` | Assigns a unique resource ID (`@+id/tvContractTitle`) to query the view via code. |
| `android:text` | Sets the displayed string content. |
| `android:textSize` | Sets font size in Scale-independent Pixels (`sp`), ensuring compatibility with user accessibility text settings. |
| `android:textStyle` | Modifies font weight (`bold`, `italic`, `normal`). |
| `android:textColor` | Defines font color in Hexadecimal format (`#1E1B18` = dark charcoal). |
| `android:lineSpacingExtra` | Adds extra space (`4dp`) between lines of text in multiline bullet points. |

---

## 🎨 3. Section Content Breakdown

### Section 1: Title & Header
- **Component ID**: `tvContractTitle`, `tvGroupInfo`, `tvCourseInfo`
- **Text Content**:
  - Title: *"Learning Contract"* (`22sp`, **bold**)
  - Subtitle: *"Groupwork # 1"* (`25sp`)
  - Course Info: *"Course: Mobile App Development | Date: Feb 2026"* (`14sp`)

### Section 2: Expectations
- **Heading**: *"Expectations"* (`18sp`, **bold**)
- **Content**: Bullet points outlining goals for Kotlin proficiency, app prototyping, and Gradle syncing.

### Section 3: Contributions
- **Heading**: *"Contributions"* (`18sp`, **bold**)
- **Content**: Individual roles detailing Kotlin/Java/XML UI development, CC17 team coding sessions, and debugging support.

### Section 4: Motivations
- **Heading**: *"Motivations"* (`18sp`, **bold**)
- **Content**: Personal drivers highlighting software problem-solving, Android career building, and portfolio creation.

### Section 5: Hindrance & Mitigations
- **Heading**: *"Hindrance & Mitigations"* (`18sp`, **bold**)
- **Special Syntax**: Uses `&amp;` for XML ampersand escaping.
- **Content**: Details challenges (time management, syntax familiarity) paired with mitigation actions.

### Section 6: Signed By
- **Heading**: *"Signed By"* (`18sp`, **bold**)
- **Content**:
  - Student Group: UniSync (Aquino, Bacani, Balidoy, Belnas, Romeo).
  - Instructor: Sir Venn Edward Nicolas.
  - Date: October 1, 2026.
