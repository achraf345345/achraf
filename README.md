<div class="card">
  <img src="https://upload.wikimedia.org/wikipedia/commons/7/77/Flag_of_Algeria.svg" alt="علم الجزائر" class="flag">
  <h1>أشرف ناصر الدين</h1>
  <p>من الجزائر، تاريخ الميلاد: 17 ديسمبر 2008</p>
  <div class="links">
    <a href="https://web.facebook.com/profile.php?id=100001863575698" target="_blank">صفحتي على فيسبوك</a>
  </div>
</div>

<div class="controls">
  <button onclick="toggleTheme()">تغيير الخلفية</button>
  <select id="languageSelector" onchange="changeLanguage()">
    <option value="ar">العربية</option>
    <option value="en">English</option>
    <option value="fr">Français</option>
  </select>
</div>

<!-- قسم المواهب -->
<div class="section">
  <h2>المواهب</h2>
  <ul>
    <li>كتابة أكواد وبرمجة المواقع الإلكترونية</li>
  </ul>
</div>

<!-- قسم الهوايات -->
<div class="section">
  <h2>الهوايات</h2>
  <ul>
    <li>ألعاب الفيديو</li>
  </ul>
</div>

<!-- قسم التعليم -->
<div class="section">
  <h2>التعليم</h2>
  <ul>
    <li>الدراسة في السنة الثالثة ثانوي</li>
  </ul>
</div>

<!-- قسم الأهداف المستقبلية -->
<div class="section">
  <h2>الأهداف المستقبلية</h2>
  <ul>
    <li>دخول مجال الذكاء الاصطناعي</li>
  </ul>
</div>

<div class="comment-section">
  <h2>أضف تعليقك</h2>
  <form id="commentForm">
    <textarea id="commentText" placeholder="اكتب تعليقك هنا..." required></textarea>
    <input type="file" id="commentImage" accept="image/*">
    <div id="voiceSection">
      <button type="button" id="startRecord" onclick="startRecording()">ابدأ التسجيل الصوتي</button>
      <button type="button" id="stopRecord" onclick="stopRecording()" disabled>أوقف التسجيل</button>
      <audio id="audioPreview" controls></audio>
    </div>
    <div>
      <button type="button" onclick="capturePhoto()">📷 التقاط صورة بالكاميرا</button>
      <video id="camera" autoplay style="display: none;"></video>
      <canvas id="snapshot" style="display: none;"></canvas>
    </div>
    <button type="submit">إرسال</button>
  </form>
  <div id="commentsContainer"></div>
</div>

<div class="visitor-counter">
  عدد الزوار: <span id="visitorCount">0</span>
</div>
<div class="stats">
  <h2>إحصائيات الصفحة</h2>
  <p><strong>عدد الزوار:</strong> <span id="visitorCount">0</span></p>
  <p><strong>عدد التعليقات:</strong> <span id="commentCount">0</span></p>
  <p><strong>عدد اللايكات:</strong> <span id="likeCount">0</span></p>
</div>

<script>
  // تحديث الإحصائيات التفاعلية
  let visitorCount = localStorage.getItem("visitorCount") || 0;
  let commentCount = JSON.parse(localStorage.getItem("comments") || "[]").length;
  let likeCount = 0;

  // تحديث العدادات
  document.getElementById("visitorCount").innerText = ++visitorCount;
  document.getElementById("commentCount").innerText = commentCount;

  // تخزين الزوار في localStorage
  localStorage.setItem("visitorCount", visitorCount);

  // تحديث عدد اللايكات
  function updateLikes() {
    const comments = JSON.parse(localStorage.getItem("comments") || "[]");
    likeCount = comments.reduce((total, comment) => total + comment.likes, 0);
    document.getElementById("likeCount").innerText = likeCount;
  }

  updateLikes(); // استدعاء الدالة لتحديث اللايكات
</script>
<link href="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.js"></script>

<div data-aos="fade-up">
  <h2>عنوان يظهر عند التمرير</h2>
  <p>هذا النص سيظهر عند التمرير إلى أسفل الصفحة.</p>
</div>

<script>
  AOS.init();
</script>
<!-- HTML -->
<div id="welcomeMessage" style="display: none;">
  <p>مرحبًا بك في صفحتي! أتمنى أن تجد معلوماتي مفيدة. إذا كنت ترغب في معرفة المزيد عني، يمكنك التصفح عبر الأقسام المختلفة!</p>
  <button onclick="closeWelcomeMessage()">شكرًا!</button>
</div>

<script>
  // JavaScript
  window.onload = function() {
    // التحقق إذا كان الزائر قد زار الصفحة من قبل باستخدام localStorage
    if (!localStorage.getItem('visited')) {
      // عرض رسالة الترحيب
      document.getElementById('welcomeMessage').style.display = 'block';
      // تعيين علامة 'visited' في localStorage لتتبع الزوار
      localStorage.setItem('visited', 'true');
    }
  };

  // إغلاق الرسالة عند الضغط على زر "شكرًا"
  function closeWelcomeMessage() {
    document.getElementById('welcomeMessage').style.display = 'none';
  }
</script>
