# BUG-09: API: буруу эсвэл таслагдсан JSON-той POST хүсэлтэд 400 биш 200 OK буцна

Орчин: Уншлагын жагсаалт v2.0, Firefox 140.15.0esr, Debian GNU/Linux, 2026-10-19
Урьдчилсан нөхцөл: node app.js-ийг шинээр асаасан (анхны 3 ном)

## Дахин гаргах алхам
1. Апп-ыг шинээр асаа (`node app.js`).
2. Өөр terminal-д: `curl -i -X POST localhost:3000/api/books -d 'буруу оролт'`
3. Дараа нь: `curl -i -X POST localhost:3000/api/books -H 'Content-Type: application/json' -d '{"title": "x", '`
4. Хоёр гаралтын эхний мөр (статус)-ийг хар.

Хүлээгдэж байсан: Спецификаци: «API: буруу JSON биетэй POST хүсэлтэд 400 алдаа буцаана.»

Бодит үр дүн: Хоёулаа `HTTP/1.1 200 OK` буцаана.

Ноцтой байдал: Major. Буруу хүсэлт амжилттай гэж тооцогдож, клиент алдааг мэдэхгүй.

Хавсралт: [evidence/bug-09-curl.txt](../evidence/bug-09-curl.txt) (эхний хүсэлт), [evidence/bug-10-curl.txt](../evidence/bug-10-curl.txt) (хоёр дахь хүсэлт). Бүтэн `curl -i` гаралт.

Олдсон аялал: Saboteur (API)
