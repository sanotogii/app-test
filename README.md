هادي خلاصة بالدارجة على **`page.tsx`**, **`layout.tsx`**، و\*\*`not-found.tsx`\*\* فـ Next.js، اللي هدرتي عليهم فالميت:

---

🔹 **`page.tsx`**
هاد الفايل هو اللي كيحكم فالمحتوى ديال الصفحة. مثلا إلا درتي `/about/page.tsx`، راه هادشي اللي غادي يبان فـ `/about` URL. هو المسؤول على الرندر ديال الصفحة.

✳️ **مثال**:

```tsx
export default function AboutPage() {
  return <h1>مرحبا بكم فـ صفحة About</h1>;
}
```

---

🔹 **`layout.tsx`**
هاد الفايل كيتستعمل باش دير structure مشترك بين بزاف ديال الصفحات، بحال الـ header, footer، و navigation.
تقدر تدير `layout.tsx` فشي فولدر (مثلا `about/layout.tsx`) وغادي يطبق غير على الصفحات اللي داخل `about/`.

✳️ **مثال**:

```tsx
export default function AboutLayout({ children }) {
  return (
    <div>
      <Header />
      {children}
      <Footer />
    </div>
  );
}
```

---

🔹 **`not-found.tsx`**
هاد الفايل كيتعرض إلا كانت شي صفحة ما كايناش (404). مثلا دخل شي واحد لـ `/about/xyz` وماكيناش، غادي يتعرض `not-found.tsx`.
تقدر تديرو فـ root ولا فـ شي route-specific directory.

✳️ **مثال**:

```tsx
export default function NotFound() {
  return <p>الصفحة ما لقيتهاش 🙁</p>;
}
```

---

📌 **الخلاصة**:

| الفايل          | الدور ديالو                                       |
| --------------- | ------------------------------------------------- |
| `page.tsx`      | كيعرض محتوى ديال صفحة معينة                       |
| `layout.tsx`    | كيعطي شكل عام مشترك للصفحات (header, footer, ...) |
| `not-found.tsx` | كيتعرض ملي المستخدم يمشي لشي route ما كايناش      |

إلا بغيتي نزيد شي أمثلة ولا نشرح بلغة تقنية أكثر، غير قولها.
