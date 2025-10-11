[Bdoor](https://github.com/m4678932/BdoorWallet.git) Wallet
name: BdoorWallet CI/CD
on"✅ تم تشغيل المحفظة بنجاح في وضع التجربة."

      - name: 🧹 إيقاف التشغيل بعد الاختبار
        run: |
          echo "🛑 إيقاف تشغيل المحفظة بعد الاختبار."
          pkill node || true
  push:
    branches: [ "main" ]
  pull_request:    branches: [ "main" ]
jobs..
  build:
    runs-on: ubuntu-latest
    steps:
      - name: 📦 نسخ الملفات من المستودع
        uses: actions/checkout@v3
      - name: ⚙️ تثبيت Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18
      - name: 🧩 تثبيت المكتبات
       run: npm install
      - name: 🏗️ بناء المشروع
        run: npm run build
      - name: 🚀 تشغيل المحفظة لاختبارها
        run: |
          echo "تشغيل محفظة بدور..."
          npm start & sleep 10
          echo
