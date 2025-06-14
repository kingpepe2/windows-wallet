# Tutorial - Mine for Blocks with Microsoft Windows

Mine for blocks with your **Windows wallet** by following the instructions below.

---

### 📥 Step 1: Download and Extract

1. [Click here to download](#) the file `kingpepe-qt-windows.zip`.
2. Open **File Explorer** and navigate to your **Downloads** directory.
3. Extract the file `kingpepe-qt-windows.zip`.

---

### ⚙️ Step 2: Create `kingpepe.conf` Configuration File

1. Press `Win + R` to open the **Run** dialog.
2. Type `notepad` and click **OK**.
3. Paste the following content into **Notepad**:

    ```ini
    rpcuser=rpc_kingpepe
    rpcpassword=dR2oBQ3K1zYMZQtJFZeAerhWxaJ5Lqeq9J2
    rpcbind=127.0.0.1
    rpcallowip=127.0.0.1
    p2pport=24028
    rpcport=24027
    listen=1
    server=1
    txindex=1
    daemon=1
    addnode=node3.walletbuilders.com
    ```

4. Click **File** → **Save As...**
5. In the **Save as type** dropdown, select **All Files (\*.\*)**
6. For **File name**, enter: `kingpepe.conf`
7. In the address bar, type `%appdata%` and press **Enter**
8. Create a new folder named `Kingpepe`, and open it.
9. Click **Save**.

---

### ⚒️ Step 3: Create the Mining Script

1. Press `Ctrl + N` in Notepad to open a new file.
2. Paste the following script:

    ```bat
    @echo off
    set SCRIPT_PATH=%cd%
    cd %SCRIPT_PATH%
    echo Press [CTRL+C] to stop mining.
    :begin
    for /f %%i in ('kingpepe-cli.exe getnewaddress') do set WALLET_ADDRESS=%%i
    kingpepe-cli.exe generatetoaddress 1 %WALLET_ADDRESS%
    goto begin
    ```

3. Click **File** → **Save As...**
4. In the **Save as type** dropdown, select **All Files (\*.\*)**
5. For **File name**, enter: `mine.bat`
6. Navigate to the folder where you extracted `kingpepe-qt-windows.zip`
7. Click **Save**

---

### 🚀 Step 4: Start Mining

1. Open your **Kingpepe Wallet** (`kingpepe-qt.exe`)
2. Double-click on `mine.bat` to begin mining.
3. Blocks will be mined to a new address each time automatically.

---

✅ Done! You are now mining Kingpepe blocks on Windows.
