# XSS (Cross-Site Scripting) qeydləri

## Nədir?
Tətbiq istifadəçi girişini təhlükəsiz emal etmədikdə, hücumçu JavaScript-i qurbanın brauzerində icra etdirə bilər.

## Növləri
| Növ | Necə işləyir | Risk |
|-----|--------------|------|
| **Reflected** | Giriş sorğuda göndərilir və cavabda dərhal əks olunur. Qurban link açmalıdır. | Orta |
| **Stored** | Giriş bazada saxlanılır, səhifəni açan hər kəs təsirlənir. | Yüksək |
| **DOM-based** | Zəiflik müştəri tərəfi JavaScript-də, server cavabı dəyişmir. | Orta/Yüksək |

## Test yanaşması (icazəli mühitdə)
1. Giriş nöqtələrini tap: axtarış, form, URL parametrləri, header-lər.
2. Girişin səhifədə **harada** əks olunduğunu müəyyən et (HTML gövdə, atribut, JS daxili).
3. Kontekstə uyğun olaraq xüsusi simvolların filtrlənib-filtrlənmədiyini yoxla.
4. Filtr varsa, **qara siyahı** məntiqinin boşluqlarını analiz et (başqa kontekstlər, kodlaşdırma).
5. JavaScript icrasını **zərərsiz** PoC ilə təsdiqlə.
6. Reproduksiya addımları, təsir və tövsiyə ilə hesabat yaz.

## Təsir
Sessiya oğurlanması (cookie HttpOnly deyilsə), saxta formalar (phishing), səhifə məzmununun dəyişdirilməsi, istifadəçi adından əməliyyatlar.

## Qorunma
- **Kontekstə uyğun output encoding** (HTML, atribut, JS, URL)
- **Content Security Policy (CSP)**
- Cookie bayraqları: `HttpOnly`, `Secure`, `SameSite`
- Müasir framework-lərin avtomatik escape mexanizmi
- Yalnız blacklist filtrinə güvənmək **düzgün deyil**

## Faydalı resurslar
- OWASP XSS Prevention Cheat Sheet
- PortSwigger Web Security Academy: XSS bölməsi
