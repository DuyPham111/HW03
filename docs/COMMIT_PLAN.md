# Danh sách commit cho các bước tiếp theo

**Repo:** https://github.com/DuyPham111/HW03 · **Nhánh:** `main`
Đề §13 yêu cầu **mỗi bước một commit**. Danh sách này là kế hoạch — tick khi commit xong.

**Định dạng:** Conventional Commits, tiếng Anh, thức mệnh lệnh, không viết hoa đầu, không chấm cuối.
`type` ∈ `docs` `feat` `fix` `chore` · `scope` ∈ `task1a` `task1b` `task2` `task3` `findings` `skills` `appendix` `repo`

```bash
git add -A && git commit -m "docs(task1b): run GUI checklist on B2 event detail screen"
git push
```

---

## Giai đoạn 0 — Chuẩn bị

- [x] `chore(repo): scaffold HW03 submission structure for scenario B` ← đã push
- [ ] `docs(repo): lock team assignment and screen split for 5-member group`
- [ ] `docs(repo): record EMS survey notes and test data fixtures for scenario B`

## Giai đoạn 1 — Task 1A · Checklist chung (15đ)

- [ ] `docs(task1a): add EMS widget survey as checklist input`
- [ ] `docs(task1a): generate IA-01 general UI items from AI draft`
- [ ] `docs(task1a): generate IA-02 form items from AI draft`
- [ ] `docs(task1a): generate IA-03 navigation items from AI draft`
- [ ] `docs(task1a): generate IA-04 feedback and state items from AI draft`
- [ ] `docs(task1a): add human-reviewed items and reasons AI missed them`
- [ ] `docs(task1a): finalise shared checklist with reference sources`

## Giai đoạn 2 — Task 1B · Chạy checklist (15đ)

- [ ] `docs(task1b): prepare execution table from shared checklist`
- [ ] `docs(task1b): run GUI checklist on B2 event detail screen`
- [ ] `docs(task1b): run GUI checklist on B3 registration form`
- [ ] `docs(task1b): run GUI checklist on B4 my-registrations and QR ticket`
- [ ] `docs(task1b): add failure evidence screenshots`
- [ ] `docs(findings): log checklist bugs as CL findings`

## Giai đoạn 3 — Task 2 · User testing (25đ)

- [ ] `docs(task2): add task scenario, metrics and SUS questionnaire`
- [ ] `docs(task2): add participant table and pilot session outcome`
- [ ] `docs(task2): add session P1 notes and SUS response`
- [ ] `docs(task2): add session P2 notes and SUS response`
- [ ] `docs(task2): add session P3 notes and SUS response`
- [ ] `docs(task2): add session P4 notes and SUS response`
- [ ] `docs(task2): add session P5 notes and SUS response`
- [ ] `docs(appendix): compute SUS scores across five participants`
- [ ] `docs(task2): rank usability findings by severity and add recommendations`
- [ ] `docs(findings): log usability issues as US findings`

## Giai đoạn 4 — Task 3 · Cross-platform (25đ)

- [ ] `docs(task3): design minimal compatibility matrix and coverage check`
- [ ] `docs(task3): run windows chrome edge firefox on three screens`
- [ ] `docs(task3): run macos safari and opera on three screens`
- [ ] `docs(task3): run android tablet and phone on three screens`
- [ ] `docs(task3): analyse failures by os, engine and device class`
- [ ] `docs(findings): log compatibility defects as CP findings`

## Giai đoạn 5 — Task 4 + 5 (10đ + 10đ)

- [ ] `docs(findings): aggregate all sources into findings log`
- [ ] `docs(findings): record google form submission timestamps`
- [ ] `docs(skills): refine agent skills after real run`
- [ ] `docs(skills): add demo video links`

## Giai đoạn 6 — Đóng gói

- [ ] `docs(appendix): complete AI audit report with human review notes`
- [ ] `docs(appendix): write AI critique within 200-300 words`
- [ ] `docs(repo): fill README test summary and self-assessment`
- [ ] `docs(appendix): export git commit log`
- [ ] `chore(repo): export PDFs and finalise submission package`

---

## Quy tắc khi commit

| Việc | Lý do |
|---|---|
| Commit **ngay sau** mỗi bước, đừng dồn | Đề chấm git log; dồn commit làm mất dấu vết quy trình |
| Ảnh bằng chứng commit **cùng** với file báo cáo trích dẫn nó | Tránh commit có link ảnh chết |
| Không commit file `.mp4` | Đã gitignore — up YouTube Unlisted, dán link vào `evidence/task2/recordings.md` |
| Xuất `appendix/git-log.txt` ở **cuối cùng** | Để log chứa đủ mọi commit |

```bash
git log --pretty=format:"%h | %ad | %s" --date=format:"%Y-%m-%d %H:%M" \
  > 23127183_HW03_AI_GUIUsability_EMS_100/appendix/git-log.txt
```
