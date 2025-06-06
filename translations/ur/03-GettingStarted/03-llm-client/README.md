<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "abbb199eb22fdffa44a0de4db6a5ea49",
  "translation_date": "2025-05-17T10:15:08+00:00",
  "source_file": "03-GettingStarted/03-llm-client/README.md",
  "language_code": "ur"
}
-->
# کلائنٹ کو LLM کے ساتھ بنانا

اب تک، آپ نے دیکھا کہ سرور اور کلائنٹ کیسے بناتے ہیں۔ کلائنٹ نے سرور کو واضح طور پر اس کے ٹولز، وسائل اور پرامپٹس کی فہرست بنانے کے لئے بلایا ہے۔ تاہم، یہ عملی طریقہ نہیں ہے۔ آپ کا صارف ایجنٹک دور میں رہتا ہے اور توقع کرتا ہے کہ وہ پرامپٹس استعمال کرے اور LLM کے ساتھ بات چیت کرے۔ آپ کے صارف کے لئے، یہ اہم نہیں ہے کہ آپ اپنی صلاحیتوں کو ذخیرہ کرنے کے لئے MCP استعمال کرتے ہیں یا نہیں، لیکن وہ توقع کرتے ہیں کہ وہ قدرتی زبان میں تعامل کریں۔ تو ہم اس مسئلے کو کیسے حل کریں؟ حل یہ ہے کہ کلائنٹ میں LLM شامل کریں۔

## جائزہ

اس سبق میں ہم کلائنٹ میں LLM شامل کرنے پر توجہ مرکوز کریں گے اور دکھائیں گے کہ یہ آپ کے صارف کے لئے بہتر تجربہ کیسے فراہم کرتا ہے۔

## سیکھنے کے مقاصد

اس سبق کے اختتام پر، آپ قابل ہوں گے:

- LLM کے ساتھ کلائنٹ بنائیں۔
- LLM کے ساتھ MCP سرور کے ساتھ بآسانی تعامل کریں۔
- کلائنٹ سائیڈ پر بہتر صارف تجربہ فراہم کریں۔

## طریقہ کار

آئیے سمجھنے کی کوشش کرتے ہیں کہ ہمیں کس طریقہ کار کو اپنانا ہے۔ LLM شامل کرنا آسان لگتا ہے، لیکن کیا ہم واقعی ایسا کریں گے؟

یہاں کلائنٹ سرور کے ساتھ کیسے تعامل کرے گا:

1. سرور کے ساتھ کنکشن قائم کریں۔

1. صلاحیتوں، پرامپٹس، وسائل اور ٹولز کی فہرست بنائیں، اور ان کی اسکیمہ محفوظ کریں۔

1. LLM شامل کریں اور محفوظ شدہ صلاحیتوں اور ان کی اسکیمہ کو ایسے فارمیٹ میں پاس کریں جو LLM سمجھتا ہو۔

1. صارف پرامپٹ کو سنبھالیں اور اسے کلائنٹ کی طرف سے درج کردہ ٹولز کے ساتھ LLM کو پاس کریں۔

بہت اچھا، اب ہم سمجھتے ہیں کہ ہم یہ کیسے کر سکتے ہیں، آئیے نیچے دیے گئے مشق میں اسے آزمائیں۔

## مشق: LLM کے ساتھ کلائنٹ بنانا

اس مشق میں، ہم اپنے کلائنٹ میں LLM شامل کرنا سیکھیں گے۔

### -1- سرور سے کنکشن کریں

آئیے پہلے اپنا کلائنٹ بنائیں:
آپ اکتوبر 2023 تک کے ڈیٹا پر تربیت یافتہ ہیں۔

### -2- سرور کی صلاحیتوں کی فہرست بنائیں

اب ہم سرور سے کنکشن کریں گے اور اس کی صلاحیتوں کے لئے پوچھیں گے:

### -3- سرور کی صلاحیتوں کو LLM ٹولز میں تبدیل کریں

سرور کی صلاحیتوں کی فہرست بنانے کے بعد اگلا قدم یہ ہے کہ انہیں ایسے فارمیٹ میں تبدیل کریں جو LLM سمجھتا ہو۔ جب ہم یہ کر لیں، تو ہم ان صلاحیتوں کو اپنے LLM کے ٹولز کے طور پر فراہم کر سکتے ہیں۔

### -4- صارف پرامپٹ درخواست کو سنبھالیں

کوڈ کے اس حصے میں، ہم صارف کی درخواستوں کو سنبھالیں گے۔

بہت اچھا، آپ نے یہ کر لیا!

## اسائنمنٹ

مشق سے کوڈ لیں اور سرور میں کچھ مزید ٹولز شامل کریں۔ پھر مشق کی طرح LLM کے ساتھ کلائنٹ بنائیں اور مختلف پرامپٹس کے ساتھ اسے آزمائیں تاکہ یہ یقینی بنایا جا سکے کہ آپ کے سرور کے تمام ٹولز کو متحرک طور پر کال کیا جا رہا ہے۔ کلائنٹ کو اس طرح بنانے کا مطلب ہے کہ آخر صارف کو بہتر تجربہ حاصل ہوگا کیونکہ وہ پرامپٹس استعمال کر سکیں گے، بجائے کہ کلائنٹ کے درست کمانڈز کے، اور کسی بھی MCP سرور کے کال ہونے سے بے خبر رہیں گے۔

## حل

[حل](/03-GettingStarted/03-llm-client/solution/README.md)

## اہم نکات

- اپنے کلائنٹ میں LLM شامل کرنا MCP سرورز کے ساتھ بات چیت کرنے کا بہتر طریقہ فراہم کرتا ہے۔
- آپ کو MCP سرور کے جواب کو کچھ ایسا تبدیل کرنے کی ضرورت ہے جو LLM سمجھ سکے۔

## نمونے

- [جاوا کیلکولیٹر](../samples/java/calculator/README.md)
- [.Net کیلکولیٹر](../../../../03-GettingStarted/samples/csharp)
- [جاوا اسکرپٹ کیلکولیٹر](../samples/javascript/README.md)
- [ٹائپ اسکرپٹ کیلکولیٹر](../samples/typescript/README.md)
- [پائتھن کیلکولیٹر](../../../../03-GettingStarted/samples/python)

## اضافی وسائل

## آگے کیا ہے

- اگلا: [Visual Studio Code کا استعمال کرتے ہوئے سرور کو استعمال کرنا](/03-GettingStarted/04-vscode/README.md)

**ڈس کلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کی کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا غلط فہمیاں ہو سکتی ہیں۔ اصل دستاویز کو اس کی مقامی زبان میں معتبر ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لئے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ ہم اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے ذمہ دار نہیں ہیں۔