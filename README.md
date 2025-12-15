# Apache Maven Installation Guide (Windows)

This tutorial will guide you through installing Apache Maven 3.9.11 on your Windows computer.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Step 1: Clone This Repository](#step-1-clone-this-repository)
- [Step 2: Extract Maven](#step-2-extract-maven)
- [Step 3: Set Environment Variables](#step-3-set-environment-variables)
- [Step 4: Verify Installation](#step-4-verify-installation)
- [Troubleshooting](#troubleshooting)

## Prerequisites

Before installing Maven, ensure you have:
- **Git** installed on your computer
- **Java Development Kit (JDK)** installed (JDK 8 or later)
- Verify Java installation by running in Command Prompt:
  ```cmd
  java -version
  ```
  You should see output showing your Java version.

## Step 1: Clone This Repository

1. Open **Command Prompt** or **Git Bash**
2. Navigate to where you want to download the repository
3. Run the following commands:

```bash
git clone [YOUR-GITHUB-REPO-URL]
cd [REPO-NAME]
```

After cloning, you should see the `apache-maven-3.9.11-bin.zip` file in the repository folder.

## Step 2: Extract Maven

1. Locate the `apache-maven-3.9.11-bin.zip` file in the cloned repository
2. Right-click on the file and select **Extract All...**
3. Choose a destination folder:
   - **Recommended:** `C:\Program Files\`
   - The extraction will create a folder named `apache-maven-3.9.11`
4. Click **Extract**

**Note:** If extracting to `C:\Program Files\`, you may need administrator privileges.

**Alternative locations:**
- `C:\apache-maven-3.9.11`
- `C:\tools\apache-maven-3.9.11`

After extraction, your Maven installation path will be:
```
C:\Program Files\apache-maven-3.9.11
```

## Step 3: Set Environment Variables

### 3.1 Set MAVEN_HOME

1. Press `Win + X` and select **System**
2. Click **Advanced system settings** (on the right side)
3. Click **Environment Variables** button
4. Under **System Variables** section, click **New**
5. Enter the following:
   - **Variable name:** `MAVEN_HOME`
   - **Variable value:** `C:\Program Files\apache-maven-3.9.11`
     (Use your actual Maven installation path)
6. Click **OK**

### 3.2 Update PATH Variable

1. Still in **Environment Variables** window
2. Under **System Variables**, find and select **Path**
3. Click **Edit**
4. Click **New**
5. Add: `%MAVEN_HOME%\bin`
6. Click **OK**
7. Click **OK** on all remaining windows

### 3.3 Optional: Set JAVA_HOME (if not already set)

Maven requires JAVA_HOME to be set. If you haven't set it:

1. Find your Java installation path (usually `C:\Program Files\Java\jdk-x.x.x`)
2. In **Environment Variables**, click **New** under **System Variables**
3. Enter:
   - **Variable name:** `JAVA_HOME`
   - **Variable value:** `C:\Program Files\Java\jdk-17` (your Java path)
4. Click **OK**

## Step 4: Verify Installation

1. **Close any open Command Prompt windows** (important!)
2. Open a **new Command Prompt**
3. Run the following command:

```cmd
mvn -version
```

You should see output similar to:

```
Apache Maven 3.9.11 (2832a4c2d3f29b3e7b098f90f6efc376e5c65c7e)
Maven home: C:\Program Files\apache-maven-3.9.11
Java version: 17.0.9, vendor: Oracle Corporation
Java home: C:\Program Files\Java\jdk-17
Default locale: en_US, platform encoding: Cp1252
OS name: "windows 11", version: "10.0", arch: "amd64", family: "windows"
```

**Congratulations!** Maven is now successfully installed on your system.

## Troubleshooting

### Issue 1: 'mvn' is not recognized as an internal or external command

**Solution:**
- Make sure you opened a **NEW** Command Prompt window after setting environment variables
- Verify that `%MAVEN_HOME%\bin` is added to the PATH variable
- Check that MAVEN_HOME is set correctly by running:
  ```cmd
  echo %MAVEN_HOME%
  ```

### Issue 2: JAVA_HOME is not set

**Error message:** "The JAVA_HOME environment variable is not defined correctly"

**Solution:**
1. Find your Java installation directory
2. Set JAVA_HOME as described in Step 3.3
3. Verify by running:
   ```cmd
   echo %JAVA_HOME%
   ```

### Issue 3: Maven version shows but wrong path

**Solution:**
- Check if you have another Maven installation on your system
- Ensure the new MAVEN_HOME path is correct
- Remove old Maven paths from the PATH variable

### Issue 4: Access Denied during extraction

**Solution:**
- Extract to a different location where you have write permissions
- Or right-click and select "Run as Administrator" when extracting

## What's Next?

Now that Maven is installed, you can:
- Create your first Maven project
- Learn Maven project structure
- Understand the POM (Project Object Model)
- Explore Maven build lifecycle

## Contributing

If you find any issues with these instructions or have suggestions for improvement, please open an issue or submit a pull request.

## License

This tutorial is provided for educational purposes.
