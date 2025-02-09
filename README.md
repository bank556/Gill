<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บไซต์ครบวงจร</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #2c2c6c;
            color: white;
            margin: 0;
            padding: 0;
        }

        .container, .admin-panel, .top-up-container {
            width: 100%;
            max-width: 400px;
            margin: 100px auto;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
            text-align: center;
        }

        h2 {
            font-size: 24px;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        button {
            background-color: #9b5fdf;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #6a3fa7;
        }

        @keyframes glow {
            0% { box-shadow: 0 0 5px #9b5fdf; }
            50% { box-shadow: 0 0 20px #9b5fdf; }
            100% { box-shadow: 0 0 5px #9b5fdf; }
        }

        button:active {
            animation: glow 1s infinite;
        }

        .action-buttons button {
            margin: 10px;
        }
    </style>
</head>
<body>
    <!-- หน้าเข้าสู่ระบบ -->
    <div class="container">
        <h2>เข้าสู่ระบบ</h2>
        <form id="login-form">
            <input type="text" id="username" placeholder="ชื่อผู้ใช้" required>
            <input type="password" id="password" placeholder="รหัสผ่าน" required>
            <button type="submit">เข้าสู่ระบบ</button>
            <p>ยังไม่มีบัญชี? <a href="javascript:void(0)" onclick="showRegister()">สมัครสมาชิก</a></p>
        </form>
    </div>

    <!-- หน้าแอดมิน -->
    <div class="admin-panel" style="display: none;">
        <h2>จัดการหลังร้าน</h2>
        <div class="action-buttons">
            <button onclick="addItem()">เพิ่มสินค้า</button>
            <button onclick="removeItem()">ลบสินค้า</button>
            <button onclick="updateItem()">อัปเดตสินค้า</button>
        </div>
        <div class="item-list">
            <!-- List of items will go here -->
        </div>
    </div>

    <!-- หน้าเติมเงิน -->
    <div class="top-up-container" style="display: none;">
        <h2>เติมเงิน</h2>
        <form id="top-up-form">
            <input type="number" id="amount" placeholder="จำนวนเงิน" required>
            <button type="submit">เติมเงิน</button>
        </form>
    </div>

    <script>
        // แสดงหน้าสมัครสมาชิก
        function showRegister() {
            document.querySelector('.container').innerHTML = `
                <h2>สมัครสมาชิก</h2>
                <form id="register-form">
                    <input type="text" id="new-username" placeholder="ชื่อผู้ใช้" required>
                    <input type="password" id="new-password" placeholder="รหัสผ่าน" required>
                    <button type="submit">สมัครสมาชิก</button>
                </form>
                <p>มีบัญชีอยู่แล้ว? <a href="javascript:void(0)" onclick="showLogin()">เข้าสู่ระบบ</a></p>
            `;
        }

        // แสดงหน้าเข้าสู่ระบบ
        function showLogin() {
            document.querySelector('.container').innerHTML = `
                <h2>เข้าสู่ระบบ</h2>
                <form id="login-form">
                    <input type="text" id="username" placeholder="ชื่อผู้ใช้" required>
                    <input type="password" id="password" placeholder="รหัสผ่าน" required>
                    <button type="submit">เข้าสู่ระบบ</button>
                    <p>ยังไม่มีบัญชี? <a href="javascript:void(0)" onclick="showRegister()">สมัครสมาชิก</a></p>
                </form>
            `;
        }

        // ฟังก์ชันจัดการสินค้า
        function addItem() {
            alert('เพิ่มสินค้าสำเร็จ');
        }

        function removeItem() {
            alert('ลบสินค้าสำเร็จ');
        }

        function updateItem() {
            alert('อัปเดตสินค้าสำเร็จ');
        }

        // ฟังก์ชันเติมเงิน
        document.getElementById('top-up-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const amount = document.getElementById('amount').value;
            alert('เติมเงินจำนวน: ' + amount + ' บาท');
        });
    </script>
</body>
</html>