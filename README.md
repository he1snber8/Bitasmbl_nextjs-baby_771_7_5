# Quickstart for Bitasmbl project (Next.js)

## 1) Install Bitasmbl-CLI package

```bash
npm i bitasmbl-cli
```

## 2) Run bitasmbl command to set up the project

```bash
bitasmbl pull --repoUrl https://github.com/he1snber8/Bitasmbl_nextjs-baby_771_7_5 --appId 7 --repoId 5
```

## 3) Enter into the main directory and start coding!

```bash
cd Bitasmbl_nextjs-baby_771_7_5
```

## Customize requirements in a way you like

Bitasmbl organizes development into requirements. Each requirement describes a feature or implementation goal and can define suggested file locations through a `paths` array.

The `paths` property acts as a mapping guideline, helping contributors understand where related code should live.

You can customize `paths` mappings through the `bitasmbl.json` file.

{"Requirement":"Build planning frontend","Paths":["**/src/app/**","**/src/pages/**","**/src/components/planner/**","**/src/features/planner/**"]}

## Requirement Evaluation

Bitasmbl includes a requirement evaluation workflow that lets contributors select a task and submit work for validation.

Run:

```bash
bitasmbl evaluate
```

Example output:

<pre>
? Available Requirements:

❯ [<span style="color:#9333ea">1</span>] <span style="color:#9333ea"> Define portfolio layout </span>            [3]
  [2] Build showcase components            [3]
  [3] Implement navigation routing         [3]
</pre>

`[x]` on the right represents the number of submission attempts remaining for a requirement.

## Example evaluation result

```tsx
/*
|--------------------------------------------------------------------------
| BITASMBL EVALUATION
|--------------------------------------------------------------------------
| REQUIREMENT:
| Implement product detail routing
|
| SCORE: 24/100
| STATUS: FAIL ✕
|
| INSIGHT:
| The page uses static product data and basic routing, but does not handle
| loading states, missing products, metadata, server data fetching, or dynamic
| route validation.
|--------------------------------------------------------------------------
*/

"use client";

import { useRouter } from "next/navigation";

export default function ProductPage() {
  const router = useRouter();

  const product = {
    id: 1,
    name: "Keyboard",
    price: 89.99,
  };

  return (
    <main className="mx-auto max-w-4xl p-6">
      <button onClick={() => router.back()}>
        Back
      </button>

      <section className="mt-6">
        <h1 className="text-3xl font-bold">
          {product.name}
        </h1>

        <p className="mt-2 text-lg">
          ${product.price}
        </p>
      </section>
    </main>
  );
}
```

## Learn More

For complete command references, workflow explanations, and additional documentation, visit:

👉 [Bitasmbl Documentation](https://bitasmbl.com/docs)
