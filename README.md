# Exam System v8 FULL FIX

Link sau deploy:
- Giáo viên: https://saodo-exam.web.app/teacher.html
- Học sinh: https://saodo-exam.web.app/student.html?v=8

Cách deploy:
1. Giải nén ZIP.
2. Mở CMD tại thư mục giải nén.
3. Chạy: firebase deploy --only hosting

Cần dán Firestore Rules:
- Mở Firebase Console > Firestore Database > Quy tắc.
- Dán nội dung firestore.rules.
- Bấm Xuất bản.

Bản này đã sửa:
- buildPersonalExamQuestions is not defined
- Mỗi học sinh đảo đề riêng theo mã phòng + họ tên + lớp + STT
- Chấm theo originalIndex
- Không đọc submissions ở phía học sinh
- Chặn nộp trùng bằng studentKey
