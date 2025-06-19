# Sell


<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام إدارة مبيعات الدكان</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Tajawal', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1e5799 0%, #207cca 51%, #2989d8 100%);
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            margin-bottom: 30px;
        }
        
        h1 {
            color: #2c3e50;
            font-size: 2.8rem;
            margin-bottom: 10px;
        }
        
        .subtitle {
            color: #7f8c8d;
            font-size: 1.2rem;
        }
        
        .main-content {
            display: flex;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .panel {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
            flex: 1;
        }
        
        .panel-title {
            color: #2980b9;
            font-size: 1.8rem;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 2px solid #eee;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #34495e;
        }
        
        input, select {
            width: 100%;
            padding: 14px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1.1rem;
            transition: border-color 0.3s;
        }
        
        input:focus, select:focus {
            border-color: #3498db;
            outline: none;
        }
        
        .btn {
            display: inline-block;
            padding: 14px 28px;
            background: #3498db;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: bold;
            transition: all 0.3s;
            text-align: center;
        }
        
        .btn:hover {
            background: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
        }
        
        .btn-danger {
            background: #e74c3c;
        }
        
        .btn-danger:hover {
            background: #c0392b;
        }
        
        .btn-success {
            background: #27ae60;
        }
        
        .btn-success:hover {
            background: #219653;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        th, td {
            padding: 15px;
            text-align: center;
            border-bottom: 1px solid #eee;
        }
        
        th {
            background-color: #f8f9fa;
            color: #2c3e50;
            font-weight: bold;
        }
        
        tr:hover {
            background-color: #f1f9ff;
        }
        
        .actions-cell {
            display: flex;
            gap: 10px;
            justify-content: center;
        }
        
        .action-btn {
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1.2rem;
            color: #7f8c8d;
            transition: color 0.3s;
        }
        
        .action-btn:hover {
            color: #3498db;
        }
        
        .delete-btn:hover {
            color: #e74c3c;
        }
        
        .invoice {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
        }
        
        .invoice-header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px dashed #eee;
        }
        
        .invoice-title {
            color: #2c3e50;
            font-size: 2.2rem;
            margin-bottom: 10px;
        }
        
        .invoice-details {
            display: flex;
            justify-content: space-between;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }
        
        .invoice-info {
            flex: 1;
            min-width: 250px;
        }
        
        .invoice-table {
            margin-bottom: 30px;
        }
        
        .invoice-total {
            text-align: right;
            font-size: 1.5rem;
            font-weight: bold;
            color: #2c3e50;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 8px;
        }
        
        .invoice-actions {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }
        
        .no-items {
            text-align: center;
            color: #7f8c8d;
            padding: 30px;
            font-size: 1.2rem;
        }
        
        .summary-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        
        .card-title {
            font-size: 1.2rem;
            color: #7f8c8d;
            margin-bottom: 15px;
        }
        
        .card-value {
            font-size: 2.5rem;
            font-weight: bold;
            color: #3498db;
        }
        
        .card-profit .card-value {
            color: #27ae60;
        }
        
        .card-loss .card-value {
            color: #e74c3c;
        }
        
        @media (max-width: 900px) {
            .main-content {
                flex-direction: column;
            }
            
            .invoice-details {
                flex-direction: column;
                gap: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>نظام إدارة مبيعات الدكان</h1>
            <p class="subtitle">أداة متكاملة لإدارة المبيعات والمشتريات وعرض الفواتير</p>
        </header>
        
        <div class="main-content">
            <div class="panel">
                <h2 class="panel-title"><i class="fas fa-plus-circle"></i> إضافة صنف جديد</h2>
                
                <div class="form-group">
                    <label for="item-name">اسم الصنف</label>
                    <input type="text" id="item-name" placeholder="أدخل اسم الصنف">
                </div>
                
                <div class="form-group">
                    <label for="item-quantity">الكمية</label>
                    <input type="number" id="item-quantity" placeholder="أدخل الكمية" min="1" value="1">
                </div>
                
                <div class="form-group">
                    <label for="item-price">السعر (ريال)</label>
                    <input type="number" id="item-price" placeholder="أدخل السعر" min="0" step="0.1">
                </div>
                
                <div class="form-group">
                    <label for="item-type">نوع العملية</label>
                    <select id="item-type">
                        <option value="sale">بيع</option>
                        <option value="purchase">شراء</option>
                    </select>
                </div>
                
                <button class="btn" id="add-item-btn">
                    <i class="fas fa-cart-plus"></i> إضافة إلى الفاتورة
                </button>
            </div>
            
            <div class="panel">
                <h2 class="panel-title"><i class="fas fa-receipt"></i> الفاتورة الحالية</h2>
                
                <div class="invoice-preview">
                    <table>
                        <thead>
                            <tr>
                                <th>الصنف</th>
                                <th>الكمية</th>
                                <th>السعر</th>
                                <th>الإجمالي</th>
                                <th>العملية</th>
                                <th>إجراءات</th>
                            </tr>
                        </thead>
                        <tbody id="invoice-items">
                            <!-- Items will be added here dynamically -->
                        </tbody>
                    </table>
                    
                    <div id="empty-invoice" class="no-items">
                        <i class="fas fa-shopping-cart" style="font-size: 3rem; margin-bottom: 15px;"></i>
                        <p>لا توجد أصناف في الفاتورة</p>
                        <p>ابدأ بإضافة أصناف باستخدام النموذج على اليسار</p>
                    </div>
                    
                    <div class="invoice-total" id="invoice-total-container" style="display: none;">
                        الإجمالي: <span id="invoice-total">0.00</span> ريال
                    </div>
                    
                    <div class="invoice-actions" id="invoice-actions" style="display: none;">
                        <button class="btn btn-success" id="finalize-btn">
                            <i class="fas fa-check-circle"></i> إنهاء البيع
                        </button>
                        <button class="btn btn-danger" id="clear-btn">
                            <i class="fas fa-trash-alt"></i> مسح الفاتورة
                        </button>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="panel">
            <h2 class="panel-title"><i class="fas fa-file-invoice-dollar"></i> فاتورة المبيعات</h2>
            
            <div class="invoice">
                <div class="invoice-header">
                    <h3 class="invoice-title">فاتورة مبيعات</h3>
                    <p>تاريخ الفاتورة: <span id="invoice-date"></span></p>
                </div>
                
                <div class="invoice-details">
                    <div class="invoice-info">
                        <p><strong>اسم المحل:</strong> دكان الخير</p>
                        <p><strong>المالك:</strong> أحمد محمد</p>
                        <p><strong>رقم السجل التجاري:</strong> 123456789</p>
                    </div>
                    <div class="invoice-info">
                        <p><strong>رقم الفاتورة:</strong> INV-<span id="invoice-number">001</span></p>
                        <p><strong>التاريخ:</strong> <span id="current-date"></span></p>
                        <p><strong>الوقت:</strong> <span id="current-time"></span></p>
                    </div>
                </div>
                
                <div class="invoice-table">
                    <table>
                        <thead>
                            <tr>
                                <th>#</th>
                                <th>الصنف</th>
                                <th>الكمية</th>
                                <th>السعر</th>
                                <th>الإجمالي</th>
                                <th>نوع العملية</th>
                            </tr>
                        </thead>
                        <tbody id="final-invoice-items">
                            <!-- Final items will be added here -->
                        </tbody>
                    </table>
                    
                    <div class="invoice-total">
                        الإجمالي النهائي: <span id="final-total">0.00</span> ريال
                    </div>
                </div>
                
                <div class="invoice-footer">
                    <p style="text-align: center; margin-top: 30px; color: #7f8c8d;">
                        شكراً لتعاملك معنا - للاستفسار: 0551234567
                    </p>
                </div>
            </div>
            
            <div class="invoice-actions" style="justify-content: center; margin-top: 30px;">
                <button class="btn" id="print-btn">
                    <i class="fas fa-print"></i> طباعة الفاتورة
                </button>
            </div>
        </div>
        
        <div class="summary-cards">
            <div class="card">
                <div class="card-title">إجمالي المبيعات اليوم</div>
                <div class="card-value">1,245 ريال</div>
            </div>
            <div class="card">
                <div class="card-title">عدد المعاملات</div>
                <div class="card-value">18</div>
            </div>
            <div class="card card-profit">
                <div class="card-title">الأرباح اليومية</div>
                <div class="card-value">312 ريال</div>
            </div>
            <div class="card card-loss">
                <div class="card-title">المشتريات</div>
                <div class="card-value">580 ريال</div>
            </div>
        </div>
    </div>
    
    <script>
        // Sample data for the invoice
        const sampleItems = [
            { id: 1, name: "أرز بسمتي 5 كجم", quantity: 2, price: 35, type: "sale" },
            { id: 2, name: "زيت زيتون 1 لتر", quantity: 3, price: 45, type: "sale" },
            { id: 3, name: "سكر 2 كجم", quantity: 5, price: 12, type: "sale" },
            { id: 4, name: "علب تونة", quantity: 24, price: 5.5, type: "purchase" }
        ];
        
        // DOM elements
        const invoiceItems = document.getElementById('invoice-items');
        const finalInvoiceItems = document.getElementById('final-invoice-items');
        const emptyInvoice = document.getElementById('empty-invoice');
        const invoiceTotalContainer = document.getElementById('invoice-total-container');
        const invoiceActions = document.getElementById('invoice-actions');
        const invoiceTotal = document.getElementById('invoice-total');
        const finalTotal = document.getElementById('final-total');
        const addItemBtn = document.getElementById('add-item-btn');
        const clearBtn = document.getElementById('clear-btn');
        const finalizeBtn = document.getElementById('finalize-btn');
        const printBtn = document.getElementById('print-btn');
        
        // Initialize current items
        let currentItems = [...sampleItems];
        
        // Update date and time
        function updateDateTime() {
            const now = new Date();
            const dateStr = now.toLocaleDateString('ar-SA');
            const timeStr = now.toLocaleTimeString('ar-SA');
            
            document.getElementById('current-date').textContent = dateStr;
            document.getElementById('current-time').textContent = timeStr;
            document.getElementById('invoice-date').textContent = dateStr;
        }
        
        // Format currency
        function formatCurrency(amount) {
            return amount.toFixed(2);
        }
        
        // Render invoice items
        function renderInvoiceItems() {
            invoiceItems.innerHTML = '';
            
            if (currentItems.length === 0) {
                emptyInvoice.style.display = 'block';
                invoiceTotalContainer.style.display = 'none';
                invoiceActions.style.display = 'none';
                return;
            }
            
            emptyInvoice.style.display = 'none';
            invoiceTotalContainer.style.display = 'block';
            invoiceActions.style.display = 'flex';
            
            let total = 0;
            
            currentItems.forEach((item, index) => {
                const row = document.createElement('tr');
                const itemTotal = item.quantity * item.price;
                total += item.type === 'sale' ? itemTotal : -itemTotal;
                
                row.innerHTML = `
                    <td>${item.name}</td>
                    <td>${item.quantity}</td>
                    <td>${formatCurrency(item.price)} ريال</td>
                    <td>${formatCurrency(itemTotal)} ريال</td>
                    <td><span class="${item.type === 'sale' ? 'sale' : 'purchase'}">${item.type === 'sale' ? 'بيع' : 'شراء'}</span></td>
                    <td class="actions-cell">
                        <button class="action-btn delete-btn" data-id="${item.id}">
                            <i class="fas fa-trash"></i>
                        </button>
                    </td>
                `;
                
                invoiceItems.appendChild(row);
            });
            
            invoiceTotal.textContent = formatCurrency(total);
        }
        
        // Render final invoice
        function renderFinalInvoice() {
            finalInvoiceItems.innerHTML = '';
            
            if (currentItems.length === 0) {
                finalTotal.textContent = '0.00';
                return;
            }
            
            let total = 0;
            
            currentItems.forEach((item, index) => {
                const row = document.createElement('tr');
                const itemTotal = item.quantity * item.price;
                total += item.type === 'sale' ? itemTotal : -itemTotal;
                
                row.innerHTML = `
                    <td>${index + 1}</td>
                    <td>${item.name}</td>
                    <td>${item.quantity}</td>
                    <td>${formatCurrency(item.price)} ريال</td>
                    <td>${formatCurrency(itemTotal)} ريال</td>
                    <td>${item.type === 'sale' ? 'بيع' : 'شراء'}</td>
                `;
                
                finalInvoiceItems.appendChild(row);
            });
            
            finalTotal.textContent = formatCurrency(total);
        }
        
        // Add new item
        function addNewItem() {
            const name = document.getElementById('item-name').value;
            const quantity = parseInt(document.getElementById('item-quantity').value);
            const price = parseFloat(document.getElementById('item-price').value);
            const type = document.getElementById('item-type').value;
            
            if (!name || !quantity || !price) {
                alert('يرجى ملء جميع الحقول');
                return;
            }
            
            const newItem = {
                id: Date.now(),
                name,
                quantity,
                price,
                type
            };
            
            currentItems.push(newItem);
            renderInvoiceItems();
            renderFinalInvoice();
            
            // Reset form
            document.getElementById('item-name').value = '';
            document.getElementById('item-quantity').value = '1';
            document.getElementById('item-price').value = '';
        }
        
        // Delete item
        function deleteItem(itemId) {
            currentItems = currentItems.filter(item => item.id !== itemId);
            renderInvoiceItems();
            renderFinalInvoice();
        }
        
        // Clear invoice
        function clearInvoice() {
            if (confirm('هل أنت متأكد أنك تريد مسح الفاتورة الحالية؟')) {
                currentItems = [];
                renderInvoiceItems();
                renderFinalInvoice();
            }
        }
        
        // Finalize invoice
        function finalizeInvoice() {
            if (currentItems.length === 0) {
                alert('لا توجد أصناف في الفاتورة');
                return;
            }
            
            alert('تم إنهاء عملية البيع بنجاح! يمكنك طباعة الفاتورة الآن.');
            
            // Generate new invoice number
            const invoiceNum = Math.floor(Math.random() * 1000);
            document.getElementById('invoice-number').textContent = invoiceNum.toString().padStart(3, '0');
            
            updateDateTime();
        }
        
        // Print invoice
        function printInvoice() {
            window.print();
        }
        
        // Event listeners
        addItemBtn.addEventListener('click', addNewItem);
        clearBtn.addEventListener('click', clearInvoice);
        finalizeBtn.addEventListener('click', finalizeInvoice);
        printBtn.addEventListener('click', printInvoice);
        
        // Event delegation for delete buttons
        invoiceItems.addEventListener('click', (e) => {
            if (e.target.closest('.delete-btn')) {
                const itemId = parseInt(e.target.closest('.delete-btn').dataset.id);
                deleteItem(itemId);
            }
        });
        
        // Initialize
        updateDateTime();
        setInterval(updateDateTime, 60000); // Update time every minute
        renderInvoiceItems();
        renderFinalInvoice();
    </script>
</body>
</html>
