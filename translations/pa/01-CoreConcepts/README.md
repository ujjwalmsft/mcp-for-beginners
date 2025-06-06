<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "4bf553c18e7e226c3d76ab0cde627d26",
  "translation_date": "2025-05-20T21:11:21+00:00",
  "source_file": "01-CoreConcepts/README.md",
  "language_code": "pa"
}
-->
# 📖 MCP ਕੋਰ ਸੰਕਲਪ: AI ਇੰਟਿਗ੍ਰੇਸ਼ਨ ਲਈ ਮਾਡਲ ਕਾਂਟੈਕਸਟ ਪ੍ਰੋਟੋਕੋਲ ਵਿੱਚ ਮਹਿਰਤ

ਮਾਡਲ ਕਾਂਟੈਕਸਟ ਪ੍ਰੋਟੋਕੋਲ (MCP) ਇੱਕ ਸ਼ਕਤੀਸ਼ਾਲੀ, ਮਿਆਰੀ ਢਾਂਚਾ ਹੈ ਜੋ ਵੱਡੇ ਭਾਸ਼ਾ ਮਾਡਲਾਂ (LLMs) ਅਤੇ ਬਾਹਰੀ ਟੂਲਾਂ, ਐਪਲੀਕੇਸ਼ਨਾਂ ਅਤੇ ਡੇਟਾ ਸਰੋਤਾਂ ਵਿਚਕਾਰ ਸੰਚਾਰ ਨੂੰ ਬਿਹਤਰ ਬਣਾਉਂਦਾ ਹੈ। ਇਹ SEO ਅਨੁਕੂਲ ਗਾਈਡ ਤੁਹਾਨੂੰ MCP ਦੇ ਮੁੱਖ ਸੰਕਲਪਾਂ ਨਾਲ ਜਾਣੂ ਕਰਵਾਏਗੀ, ਜਿਸ ਨਾਲ ਤੁਸੀਂ ਇਸ ਦੀ ਕਲਾਇੰਟ-ਸਰਵਰ ਆਰਕੀਟੈਕਚਰ, ਜਰੂਰੀ ਹਿੱਸਿਆਂ, ਸੰਚਾਰ ਦੇ ਤਰੀਕਿਆਂ ਅਤੇ ਅਮਲਦਾਰੀ ਦੇ ਸਰੋਤਿਆਂ ਨੂੰ ਸਮਝ ਸਕੋਗੇ।

## ਓਵਰਵਿਊ

ਇਸ ਪਾਠ ਵਿੱਚ ਅਸੀਂ ਮਾਡਲ ਕਾਂਟੈਕਸਟ ਪ੍ਰੋਟੋਕੋਲ (MCP) ਪਰਿਸਰ ਦੀ ਮੂਲ ਆਰਕੀਟੈਕਚਰ ਅਤੇ ਹਿੱਸਿਆਂ ਦੀ ਜਾਂਚ ਕਰਾਂਗੇ। ਤੁਸੀਂ ਕਲਾਇੰਟ-ਸਰਵਰ ਆਰਕੀਟੈਕਚਰ, ਮੁੱਖ ਹਿੱਸਿਆਂ ਅਤੇ ਸੰਚਾਰ ਦੇ ਤਰੀਕਿਆਂ ਬਾਰੇ ਜਾਣੋਗੇ ਜੋ MCP ਦੀਆਂ ਇੰਟਰੈਕਸ਼ਨਾਂ ਨੂੰ ਸੰਚਾਲਿਤ ਕਰਦੇ ਹਨ।

## 👩‍🎓 ਮੁੱਖ ਸਿੱਖਣ ਵਾਲੇ ਲਕੜੀ

ਇਸ ਪਾਠ ਦੇ ਅੰਤ ਤੱਕ, ਤੁਸੀਂ:

- MCP ਕਲਾਇੰਟ-ਸਰਵਰ ਆਰਕੀਟੈਕਚਰ ਨੂੰ ਸਮਝੋਗੇ।
- Hosts, Clients, ਅਤੇ Servers ਦੇ ਕਿਰਦਾਰ ਅਤੇ ਜ਼ਿੰਮੇਵਾਰੀਆਂ ਦੀ ਪਛਾਣ ਕਰੋਗੇ।
- MCP ਨੂੰ ਇੱਕ ਲਚਕੀਲਾ ਇੰਟਿਗ੍ਰੇਸ਼ਨ ਲੇਅਰ ਬਣਾਉਣ ਵਾਲੀਆਂ ਮੁੱਖ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਦਾ ਵਿਸ਼ਲੇਸ਼ਣ ਕਰੋਗੇ।
- MCP ਪਰਿਸਰ ਵਿੱਚ ਜਾਣਕਾਰੀ ਕਿਵੇਂ ਬਹਿੰਦੀ ਹੈ, ਇਹ ਸਿੱਖੋਗੇ।
- .NET, Java, Python, ਅਤੇ JavaScript ਵਿੱਚ ਕੋਡ ਉਦਾਹਰਣਾਂ ਰਾਹੀਂ ਪ੍ਰਯੋਗਿਕ ਜਾਣਕਾਰੀਆਂ ਪ੍ਰਾਪਤ ਕਰੋਗੇ।

## 🔎 MCP ਆਰਕੀਟੈਕਚਰ: ਇੱਕ ਗਹਿਰਾਈ ਵਾਲੀ ਨਜ਼ਰ

MCP ਪਰਿਸਰ ਇੱਕ ਕਲਾਇੰਟ-ਸਰਵਰ ਮਾਡਲ 'ਤੇ ਬਣਿਆ ਹੈ। ਇਹ ਮਾਡੂਲਰ ਢਾਂਚਾ AI ਐਪਲੀਕੇਸ਼ਨਾਂ ਨੂੰ ਟੂਲਾਂ, ਡੇਟਾਬੇਸ, APIs, ਅਤੇ ਸੰਦਰਭਿਕ ਸਰੋਤਾਂ ਨਾਲ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਤਰੀਕੇ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ। ਆਓ ਇਸ ਆਰਕੀਟੈਕਚਰ ਨੂੰ ਇਸਦੇ ਮੁੱਖ ਹਿੱਸਿਆਂ ਵਿੱਚ ਵੰਡ ਕੇ ਵੇਖੀਏ।

### 1. Hosts

ਮਾਡਲ ਕਾਂਟੈਕਸਟ ਪ੍ਰੋਟੋਕੋਲ (MCP) ਵਿੱਚ, Hosts ਇੱਕ ਮੁੱਖ ਭੂਮਿਕਾ ਨਿਭਾਉਂਦੇ ਹਨ ਜਿੱਥੇ ਉਪਭੋਗਤਾ ਪ੍ਰੋਟੋਕੋਲ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਦੇ ਹਨ। Hosts ਉਹ ਐਪਲੀਕੇਸ਼ਨ ਜਾਂ ਵਾਤਾਵਰਣ ਹਨ ਜੋ MCP ਸਰਵਰਾਂ ਨਾਲ ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦੇ ਹਨ ਤਾਂ ਜੋ ਡੇਟਾ, ਟੂਲਾਂ ਅਤੇ ਪ੍ਰਾਂਪਟਾਂ ਤੱਕ ਪਹੁੰਚ ਸਕਣ। Hosts ਦੇ ਉਦਾਹਰਣਾਂ ਵਿੱਚ ਇੰਟੀਗ੍ਰੇਟਡ ਡਿਵੈਲਪਮੈਂਟ ਐਨਵਾਇਰੰਮੈਂਟ (IDEs) ਜਿਵੇਂ Visual Studio Code, AI ਟੂਲਾਂ ਜਿਵੇਂ Claude Desktop, ਜਾਂ ਖਾਸ ਟਾਸਕਾਂ ਲਈ ਬਣਾਏ ਗਏ ਕਸਟਮ ਏਜੰਟ ਸ਼ਾਮਲ ਹਨ।

**Hosts** ਉਹ LLM ਐਪਲੀਕੇਸ਼ਨ ਹਨ ਜੋ ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦੇ ਹਨ। ਉਹ:

- AI ਮਾਡਲਾਂ ਨਾਲ ਜਵਾਬ ਬਣਾਉਣ ਲਈ ਕੰਮ ਕਰਦੇ ਜਾਂ ਇੰਟਰੈਕਟ ਕਰਦੇ ਹਨ।
- MCP ਸਰਵਰਾਂ ਨਾਲ ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦੇ ਹਨ।
- ਗੱਲਬਾਤ ਦੇ ਪ੍ਰਵਾਹ ਅਤੇ ਉਪਭੋਗਤਾ ਇੰਟਰਫੇਸ ਨੂੰ ਸੰਭਾਲਦੇ ਹਨ।
- ਪਰਮਿਸ਼ਨ ਅਤੇ ਸੁਰੱਖਿਆ ਸੀਮਾਵਾਂ ਨੂੰ ਕੰਟਰੋਲ ਕਰਦੇ ਹਨ।
- ਡੇਟਾ ਸਾਂਝਾ ਕਰਨ ਅਤੇ ਟੂਲ ਚਲਾਉਣ ਲਈ ਉਪਭੋਗਤਾ ਦੀ ਸਹਿਮਤੀ ਨੂੰ ਸੰਭਾਲਦੇ ਹਨ।

### 2. Clients

Clients ਉਹ ਜਰੂਰੀ ਹਿੱਸੇ ਹਨ ਜੋ Hosts ਅਤੇ MCP ਸਰਵਰਾਂ ਵਿਚਕਾਰ ਇੰਟਰੈਕਸ਼ਨ ਨੂੰ ਸੁਗਮ ਬਣਾਉਂਦੇ ਹਨ। Clients ਮੱਧਸਥ ਹਨ ਜੋ Hosts ਨੂੰ MCP ਸਰਵਰਾਂ ਵੱਲੋਂ ਦਿੱਤੀਆਂ ਗਈਆਂ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਦੀ ਪਹੁੰਚ ਅਤੇ ਵਰਤੋਂ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦੇ ਹਨ। ਉਹ MCP ਆਰਕੀਟੈਕਚਰ ਵਿੱਚ ਸਾਫ਼ ਸੰਚਾਰ ਅਤੇ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਡੇਟਾ ਅਦਾਨ-ਪ੍ਰਦਾਨ ਨੂੰ ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ।

**Clients** ਹੋਸਟ ਐਪਲੀਕੇਸ਼ਨ ਦੇ ਅੰਦਰ ਕੰਨੈਕਟਰ ਹੁੰਦੇ ਹਨ। ਉਹ:

- ਸਰਵਰਾਂ ਨੂੰ ਪ੍ਰਾਂਪਟਾਂ/ਹਦਾਇਤਾਂ ਨਾਲ ਬੇਨਤੀਆਂ ਭੇਜਦੇ ਹਨ।
- ਸਰਵਰਾਂ ਨਾਲ ਸਮਰੱਥਾਵਾਂ ਦੀ ਗੱਲਬਾਤ ਕਰਦੇ ਹਨ।
- ਮਾਡਲਾਂ ਤੋਂ ਟੂਲ ਚਲਾਉਣ ਦੀਆਂ ਬੇਨਤੀਆਂ ਸੰਭਾਲਦੇ ਹਨ।
- ਉਪਭੋਗਤਾਵਾਂ ਨੂੰ ਜਵਾਬ ਪ੍ਰਕਿਰਿਆ ਅਤੇ ਦਿਖਾਉਂਦੇ ਹਨ।

### 3. Servers

Servers MCP ਕਲਾਇੰਟਾਂ ਤੋਂ ਬੇਨਤੀਆਂ ਸੰਭਾਲਦੇ ਹਨ ਅਤੇ ਉਚਿਤ ਜਵਾਬ ਦਿੰਦੇ ਹਨ। ਉਹ ਡੇਟਾ ਪ੍ਰਾਪਤੀ, ਟੂਲ ਚਲਾਉਣ ਅਤੇ ਪ੍ਰਾਂਪਟ ਬਣਾਉਣ ਵਰਗੀਆਂ ਕਈ ਕਾਰਵਾਈਆਂ ਦਾ ਪ੍ਰਬੰਧ ਕਰਦੇ ਹਨ। Servers ਇਹ ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ ਕਿ ਕਲਾਇੰਟਾਂ ਅਤੇ Hosts ਵਿਚਕਾਰ ਸੰਚਾਰ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਅਤੇ ਭਰੋਸੇਯੋਗ ਹੈ, ਅਤੇ ਇੰਟਰੈਕਸ਼ਨ ਪ੍ਰਕਿਰਿਆ ਦੀ ਸਚਾਈ ਨੂੰ ਕਾਇਮ ਰੱਖਦੇ ਹਨ।

**Servers** ਉਹ ਸੇਵਾਵਾਂ ਹਨ ਜੋ ਸੰਦਰਭ ਅਤੇ ਸਮਰੱਥਾਵਾਂ ਪ੍ਰਦਾਨ ਕਰਦੀਆਂ ਹਨ। ਉਹ:

- ਉਪਲਬਧ ਫੀਚਰਾਂ (ਸਰੋਤ, ਪ੍ਰਾਂਪਟ, ਟੂਲ) ਨੂੰ ਰਜਿਸਟਰ ਕਰਦੇ ਹਨ।
- ਕਲਾਇੰਟ ਤੋਂ ਟੂਲ ਕਾਲਾਂ ਨੂੰ ਪ੍ਰਾਪਤ ਕਰਕੇ ਚਲਾਉਂਦੇ ਹਨ।
- ਮਾਡਲ ਜਵਾਬਾਂ ਨੂੰ ਵਧੀਆ ਬਣਾਉਣ ਲਈ ਸੰਦਰਭਿਕ ਜਾਣਕਾਰੀ ਦਿੰਦੇ ਹਨ।
- ਨਤੀਜੇ ਵਾਪਸ ਕਲਾਇੰਟ ਨੂੰ ਭੇਜਦੇ ਹਨ।
- ਜਰੂਰਤ ਪੈਣ 'ਤੇ ਇੰਟਰੈਕਸ਼ਨਾਂ ਦੌਰਾਨ ਸਥਿਤੀ ਕਾਇਮ ਰੱਖਦੇ ਹਨ।

ਕੋਈ ਵੀ ਵਿਅਕਤੀ ਖਾਸ ਫੰਕਸ਼ਨਾਲਿਟੀ ਨਾਲ ਮਾਡਲ ਸਮਰੱਥਾਵਾਂ ਨੂੰ ਵਧਾਉਣ ਲਈ ਸਰਵਰ ਵਿਕਸਤ ਕਰ ਸਕਦਾ ਹੈ।

### 4. Server Features

MCP ਸਰਵਰ ਮੁੱਖ ਤੱਤ ਪ੍ਰਦਾਨ ਕਰਦੇ ਹਨ ਜੋ ਕਲਾਇੰਟਾਂ, ਹੋਸਟਾਂ ਅਤੇ ਭਾਸ਼ਾ ਮਾਡਲਾਂ ਵਿਚਕਾਰ ਸਮਰੱਥ ਇੰਟਰੈਕਸ਼ਨ ਨੂੰ ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ। ਇਹ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ MCP ਦੀ ਸਮਰੱਥਾ ਨੂੰ ਵਧਾਉਂਦੀਆਂ ਹਨ ਜਿਵੇਂ ਕਿ ਢਾਂਚਾਬੱਧ ਸੰਦਰਭ, ਟੂਲ ਅਤੇ ਪ੍ਰਾਂਪਟ।

MCP ਸਰਵਰ ਹੇਠ ਲਿਖੀਆਂ ਕਿਸੇ ਵੀ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਦੀ ਪੇਸ਼ਕਸ਼ ਕਰ ਸਕਦੇ ਹਨ:

#### 📑 Resources

MCP ਵਿੱਚ ਸਰੋਤ ਵੱਖ-ਵੱਖ ਕਿਸਮ ਦੇ ਸੰਦਰਭ ਅਤੇ ਡੇਟਾ ਨੂੰ ਸ਼ਾਮਲ ਕਰਦੇ ਹਨ ਜੋ ਉਪਭੋਗਤਾਵਾਂ ਜਾਂ AI ਮਾਡਲਾਂ ਵੱਲੋਂ ਵਰਤੇ ਜਾ ਸਕਦੇ ਹਨ। ਇਹ ਵਿੱਚ ਸ਼ਾਮਲ ਹਨ:

- **ਸੰਦਰਭਿਕ ਡੇਟਾ**: ਜਾਣਕਾਰੀ ਅਤੇ ਸੰਦਰਭ ਜੋ ਉਪਭੋਗਤਾ ਜਾਂ AI ਮਾਡਲ ਫੈਸਲੇ ਅਤੇ ਕਾਰਜਾਂ ਲਈ ਵਰਤ ਸਕਦੇ ਹਨ।
- **ਨੋਲੇਜ ਬੇਸ ਅਤੇ ਦਸਤਾਵੇਜ਼ ਰਿਪੋਜ਼ਿਟਰੀਜ਼**: ਸੰਰਚਿਤ ਅਤੇ ਅਸੰਰਚਿਤ ਡੇਟਾ ਦੇ ਸੰਗ੍ਰਹਿ, ਜਿਵੇਂ ਲੇਖ, ਮੈਨੂਅਲ, ਅਤੇ ਖੋਜ ਪੇਪਰ, ਜੋ ਕੀਮਤੀ ਜਾਣਕਾਰੀਆਂ ਦਿੰਦੇ ਹਨ।
- **ਲੋਕਲ ਫਾਈਲਾਂ ਅਤੇ ਡੇਟਾਬੇਸ**: ਜੰਤਰਾਂ 'ਤੇ ਸਥਾਨਕ ਸਟੋਰ ਕੀਤੀ ਡੇਟਾ ਜਾਂ ਡੇਟਾਬੇਸ, ਜੋ ਪ੍ਰੋਸੈਸਿੰਗ ਅਤੇ ਵਿਸ਼ਲੇਸ਼ਣ ਲਈ ਉਪਲਬਧ ਹੈ।
- **APIs ਅਤੇ ਵੈੱਬ ਸੇਵਾਵਾਂ**: ਬਾਹਰੀ ਇੰਟਰਫੇਸ ਅਤੇ ਸੇਵਾਵਾਂ ਜੋ ਵਾਧੂ ਡੇਟਾ ਅਤੇ ਕਾਰਜਸ਼ੀਲਤਾਵਾਂ ਦਿੰਦੇ ਹਨ, ਵੱਖ-ਵੱਖ ਆਨਲਾਈਨ ਸਰੋਤਾਂ ਅਤੇ ਟੂਲਾਂ ਨਾਲ ਇੰਟੀਗ੍ਰੇਸ਼ਨ ਯੋਗ।

ਇੱਕ ਸਰੋਤ ਦਾ ਉਦਾਹਰਣ ਡੇਟਾਬੇਸ ਸਕੀਮਾ ਜਾਂ ਫਾਈਲ ਹੋ ਸਕਦੀ ਹੈ ਜਿਸ ਨੂੰ ਇਸ ਤਰ੍ਹਾਂ ਐਕਸੈੱਸ ਕੀਤਾ ਜਾ ਸਕਦਾ ਹੈ:

```text
file://log.txt
database://schema
```

### 🤖 Prompts

MCP ਵਿੱਚ ਪ੍ਰਾਂਪਟ ਵੱਖ-ਵੱਖ ਪਹਿਲਾਂ ਤੋਂ ਤਿਆਰ ਕੀਤੇ ਟੈਮਪਲੇਟ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨ ਪੈਟਰਨ ਸ਼ਾਮਲ ਹਨ ਜੋ ਉਪਭੋਗਤਾ ਦੇ ਕੰਮਕਾਜ ਨੂੰ ਆਸਾਨ ਬਣਾਉਂਦੇ ਹਨ ਅਤੇ ਸੰਚਾਰ ਨੂੰ ਸੁਧਾਰਦੇ ਹਨ। ਇਹ ਵਿੱਚ ਸ਼ਾਮਲ ਹਨ:

- **ਟੈਮਪਲੇਟ ਕੀਤੇ ਸੁਨੇਹੇ ਅਤੇ ਵਰਕਫਲੋਜ਼**: ਪਹਿਲਾਂ ਤੋਂ ਬਣਾਏ ਗਏ ਸੁਨੇਹੇ ਅਤੇ ਪ੍ਰਕਿਰਿਆਵਾਂ ਜੋ ਉਪਭੋਗਤਾਵਾਂ ਨੂੰ ਖਾਸ ਕੰਮਾਂ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨਾਂ ਵਿੱਚ ਮਦਦ ਕਰਦੀਆਂ ਹਨ।
- **ਪਹਿਲਾਂ ਤੋਂ ਨਿਰਧਾਰਤ ਇੰਟਰੈਕਸ਼ਨ ਪੈਟਰਨ**: ਮਿਆਰੀ ਕਾਰਵਾਈਆਂ ਅਤੇ ਜਵਾਬਾਂ ਦੇ ਲੜੀਵਾਰ ਕਦਮ ਜੋ ਸੰਚਾਰ ਨੂੰ ਲਗਾਤਾਰ ਅਤੇ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਬਣਾਉਂਦੇ ਹਨ।
- **ਖਾਸ ਗੱਲਬਾਤ ਟੈਮਪਲੇਟ**: ਖਾਸ ਕਿਸਮ ਦੀਆਂ ਗੱਲਬਾਤਾਂ ਲਈ ਕਸਟਮਾਈਜ਼ਡ ਟੈਮਪਲੇਟ, ਜੋ ਸੰਬੰਧਤ ਅਤੇ ਸੰਦਰਭਿਕ ਤੌਰ 'ਤੇ ਢੁਕਵਾਂ ਇੰਟਰੈਕਸ਼ਨ ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ।

ਇੱਕ ਪ੍ਰਾਂਪਟ ਟੈਮਪਲੇਟ ਇਸ ਤਰ੍ਹਾਂ ਹੋ ਸਕਦਾ ਹੈ:

```markdown
Generate a product slogan based on the following {{product}} with the following {{keywords}}
```

#### ⛏️ Tools

MCP ਵਿੱਚ ਟੂਲ ਉਹ ਫੰਕਸ਼ਨ ਹਨ ਜੋ AI ਮਾਡਲ ਖਾਸ ਟਾਸਕ ਕਰਨ ਲਈ ਚਲਾ ਸਕਦਾ ਹੈ। ਇਹ ਟੂਲ AI ਮਾਡਲ ਦੀ ਸਮਰੱਥਾ ਨੂੰ ਵਧਾਉਂਦੇ ਹਨ ਅਤੇ ਸੰਰਚਿਤ ਅਤੇ ਭਰੋਸੇਯੋਗ ਓਪਰੇਸ਼ਨਾਂ ਪ੍ਰਦਾਨ ਕਰਦੇ ਹਨ। ਮੁੱਖ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਹਨ:

- **AI ਮਾਡਲ ਲਈ ਚਲਾਏ ਜਾਣ ਵਾਲੇ ਫੰਕਸ਼ਨ**: ਟੂਲ ਐਜਿਹੇ ਫੰਕਸ਼ਨ ਹਨ ਜੋ AI ਮਾਡਲ ਵੱਲੋਂ ਵੱਖ-ਵੱਖ ਕੰਮ ਕਰਨ ਲਈ ਕਾਲ ਕੀਤੇ ਜਾ ਸਕਦੇ ਹਨ।
- **ਵੱਖਰਾ ਨਾਮ ਅਤੇ ਵਰਣਨ**: ਹਰ ਟੂਲ ਦਾ ਇੱਕ ਵਿਲੱਖਣ ਨਾਮ ਅਤੇ ਵਿਸਥਾਰਪੂਰਵਕ ਵਰਣਨ ਹੁੰਦਾ ਹੈ ਜੋ ਇਸਦੇ ਉਦੇਸ਼ ਅਤੇ ਕਾਰਜਸ਼ੀਲਤਾ ਨੂੰ ਸਮਝਾਉਂਦਾ ਹੈ।
- **ਪੈਰਾਮੀਟਰ ਅਤੇ ਨਤੀਜੇ**: ਟੂਲ ਖਾਸ ਪੈਰਾਮੀਟਰ ਲੈਂਦੇ ਹਨ ਅਤੇ ਸੰਰਚਿਤ ਨਤੀਜੇ ਵਾਪਸ ਕਰਦੇ ਹਨ, ਜੋ ਨਤੀਜਿਆਂ ਨੂੰ ਲਗਾਤਾਰ ਅਤੇ ਪੂਰੀ ਤਰ੍ਹਾਂ ਅਨੁਮਾਨਯੋਗ ਬਣਾਉਂਦੇ ਹਨ।
- **ਵੱਖ-ਵੱਖ ਫੰਕਸ਼ਨ**: ਟੂਲ ਵੱਖ-ਵੱਖ ਕੰਮ ਕਰਦੇ ਹਨ ਜਿਵੇਂ ਵੈੱਬ ਖੋਜ, ਗਣਨਾ, ਅਤੇ ਡੇਟਾਬੇਸ ਪੁੱਛਗਿੱਛ।

ਇੱਕ ਉਦਾਹਰਣ ਟੂਲ ਇਸ ਤਰ੍ਹਾਂ ਹੋ ਸਕਦਾ ਹੈ:

```typescript
server.tool(
  "GetProducts",
  {
    pageSize: z.string().optional(),
    pageCount: z.string().optional()
  }, () => {
    // return results from API
  }
)
```

## Client Features

MCP ਵਿੱਚ, clients ਸਰਵਰਾਂ ਨੂੰ ਕਈ ਮੁੱਖ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਦਿੰਦੇ ਹਨ, ਜੋ ਪ੍ਰੋਟੋਕੋਲ ਦੇ ਕੁੱਲ ਕਾਰਜਸ਼ੀਲਤਾ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨ ਨੂੰ ਸੁਧਾਰਦੇ ਹਨ। ਇੱਕ ਪ੍ਰਮੁੱਖ ਵਿਸ਼ੇਸ਼ਤਾ Sampling ਹੈ।

### 👉 Sampling

- **ਸਰਵਰ ਦੁਆਰਾ ਸ਼ੁਰੂ ਕੀਤੀਆਂ ਗਈਆਂ ਏਜੰਟਿਕ ਵਿਹਾਰਾਂ**: Clients ਸਰਵਰਾਂ ਨੂੰ ਖ਼ਾਸ ਕਾਰਵਾਈਆਂ ਜਾਂ ਵਿਹਾਰਾਂ ਨੂੰ ਖੁਦਮੁਖਤਿਆਰ ਤਰੀਕੇ ਨਾਲ ਸ਼ੁਰੂ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦੇ ਹਨ, ਜੋ ਸਿਸਟਮ ਦੀ ਗਤੀਸ਼ੀਲ ਸਮਰੱਥਾ ਨੂੰ ਵਧਾਉਂਦਾ ਹੈ।
- **Recursive LLM ਇੰਟਰੈਕਸ਼ਨ**: ਇਹ ਵਿਸ਼ੇਸ਼ਤਾ ਵੱਡੇ ਭਾਸ਼ਾ ਮਾਡਲਾਂ (LLMs) ਨਾਲ ਦੁਹਰਾਈ ਵਾਲੀਆਂ ਇੰਟਰੈਕਸ਼ਨਾਂ ਦੀ ਆਗਿਆ ਦਿੰਦੀ ਹੈ, ਜੋ ਟਾਸਕਾਂ ਦੀ ਵੱਧ ਜਟਿਲ ਅਤੇ ਕਈ ਵਾਰੀ ਪ੍ਰਕਿਰਿਆ ਨੂੰ ਯਕੀਨੀ ਬਣਾਉਂਦੀ ਹੈ।
- **ਵਾਧੂ ਮਾਡਲ ਕੰਪਲੀਸ਼ਨ ਦੀ ਮੰਗ**: ਸਰਵਰ ਮਾਡਲ ਤੋਂ ਵਾਧੂ ਜਵਾਬ ਮੰਗ ਸਕਦੇ ਹਨ, ਤਾਂ ਜੋ ਜਵਾਬ ਪੂਰੇ ਅਤੇ ਸੰਦਰਭਿਕ ਤੌਰ 'ਤੇ ਢੁਕਵਾਂ ਹੋਣ।

## MCP ਵਿੱਚ ਜਾਣਕਾਰੀ ਦਾ ਪ੍ਰਵਾਹ

MCP ਇੱਕ ਢਾਂਚਾਬੱਧ ਜਾਣਕਾਰੀ ਦਾ ਪ੍ਰਵਾਹ ਨਿਰਧਾਰਤ ਕਰਦਾ ਹੈ ਜੋ Hosts, Clients, Servers, ਅਤੇ ਮਾਡਲਾਂ ਵਿਚਕਾਰ ਹੁੰਦਾ ਹੈ। ਇਸ ਪ੍ਰਵਾਹ ਨੂੰ ਸਮਝਣਾ ਇਹ ਸਾਫ਼ ਕਰਦਾ ਹੈ ਕਿ ਉਪਭੋਗਤਾ ਦੀਆਂ ਬੇਨਤੀਆਂ ਕਿਵੇਂ ਪ੍ਰਕਿਰਿਆਤਮਕ ਹੁੰਦੀਆਂ ਹਨ ਅਤੇ ਬਾਹਰੀ ਟੂਲਾਂ ਅਤੇ ਡੇਟਾ ਕਿਵੇਂ ਮਾਡਲ ਜਵਾਬਾਂ ਵਿੱਚ ਸ਼ਾਮਲ ਕੀਤੇ ਜਾਂਦੇ ਹਨ।

- **Host ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦਾ ਹੈ**  
  ਹੋਸਟ ਐਪਲੀਕੇਸ਼ਨ (ਜਿਵੇਂ IDE ਜਾਂ ਚੈਟ ਇੰਟਰਫੇਸ) ਆਮ ਤੌਰ 'ਤੇ STDIO, WebSocket, ਜਾਂ ਹੋਰ ਸਮਰਥਿਤ ਟਰਾਂਸਪੋਰਟ ਰਾਹੀਂ MCP ਸਰਵਰ ਨਾਲ ਕਨੈਕਸ਼ਨ ਬਣਾਉਂਦਾ ਹੈ।

- **ਸਮਰੱਥਾ ਦੀ ਗੱਲਬਾਤ**  
  ਕਲਾਇੰਟ (ਹੋਸਟ ਵਿੱਚ ਸਮਾਇਆ ਹੋਇਆ) ਅਤੇ ਸਰਵਰ ਆਪਣੇ ਸਮਰਥਿਤ ਫੀਚਰਾਂ, ਟੂਲਾਂ, ਸਰੋਤਾਂ, ਅਤੇ ਪ੍ਰੋਟੋਕੋਲ ਵਰਜ਼ਨਾਂ ਬਾਰੇ ਜਾਣਕਾਰੀ ਸਾਂਝੀ ਕਰਦੇ ਹਨ। ਇਸ ਨਾਲ ਦੋਹਾਂ ਪਾਸਿਆਂ ਨੂੰ ਪਤਾ ਲੱਗਦਾ ਹੈ ਕਿ ਸੈਸ਼ਨ ਲਈ ਕਿਹੜੀਆਂ ਸਮਰੱਥਾਵਾਂ ਉਪਲਬਧ ਹਨ।

- **ਉਪਭੋਗਤਾ ਦੀ ਬੇਨਤੀ**  
  ਉਪਭੋਗਤਾ ਹੋਸਟ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਦਾ ਹੈ (ਜਿਵੇਂ ਪ੍ਰਾਂਪਟ ਜਾਂ ਕਮਾਂਡ ਦਿੰਦਾ ਹੈ)। ਹੋਸਟ ਇਹ ਇਨਪੁੱਟ ਲੈਂਦਾ ਹੈ ਅਤੇ ਪ੍ਰਕਿਰਿਆ ਲਈ ਕਲਾਇੰਟ ਨੂੰ ਭੇਜਦਾ ਹੈ।

- **ਸਰੋਤ ਜਾਂ ਟੂਲ ਦੀ ਵਰਤੋਂ**  
  - ਕਲਾਇੰਟ ਸਰਵਰ ਤੋਂ ਵਾਧੂ ਸੰਦਰਭ ਜਾਂ ਸਰੋਤ (ਜਿਵੇਂ ਫਾਈਲਾਂ, ਡੇਟਾਬੇਸ ਐਂਟਰੀਜ਼, ਜਾਂ ਨੋਲੇਜ ਬੇਸ ਆਰਟਿਕਲ) ਮੰਗ ਸਕਦਾ ਹੈ ਤਾਂ ਜੋ ਮਾਡਲ ਦੀ ਸਮਝ ਨੂੰ ਸਮਰੱਥ ਬਣਾਇਆ ਜਾ ਸਕੇ।  
  - ਜੇ ਮਾਡਲ ਨੂੰ ਲੱਗਦਾ ਹੈ ਕਿ ਟੂਲ ਦੀ ਲੋੜ ਹੈ (ਜਿਵੇਂ ਡੇਟਾ ਲੈਣ, ਗਣਨਾ ਕਰਨ, ਜਾਂ API ਕਾਲ ਕਰਨ ਲਈ), ਤਾਂ ਕਲਾਇੰਟ ਟੂਲ ਕਾਲ ਬੇਨਤੀ ਸਰਵਰ ਨੂੰ ਭੇਜਦਾ ਹੈ ਜਿਸ ਵਿੱਚ ਟੂਲ ਦਾ ਨਾਮ ਅਤੇ ਪੈਰਾਮੀਟਰ ਸ਼ਾਮਲ ਹੁੰਦੇ ਹਨ।

- **ਸਰਵਰ ਚਲਾਉਣਾ**  
  ਸਰਵਰ ਸਰੋਤ ਜਾਂ ਟੂਲ ਦੀ ਬੇਨਤੀ ਪ੍ਰਾਪਤ ਕਰਦਾ ਹੈ, ਜਰੂਰੀ ਕਾਰਵਾਈਆਂ ਕਰਦਾ ਹੈ (ਜਿਵੇਂ ਫੰਕਸ਼ਨ ਚਲਾਉਣਾ, ਡੇਟਾਬੇਸ ਪੁੱਛਗਿੱਛ, ਜਾਂ ਫਾਈਲ ਪ੍ਰਾਪਤ ਕਰਨਾ), ਅਤੇ ਨਤੀਜੇ ਕਲਾਇੰਟ ਨੂੰ ਸੰਰਚਿਤ ਫਾਰਮੈਟ ਵਿੱਚ ਵਾਪਸ ਭੇਜਦਾ ਹੈ।

- **ਜਵਾਬ ਬਣਾਉਣਾ**  
  ਕਲਾਇੰਟ ਸਰਵਰ ਦੇ ਜਵਾਬਾਂ (ਸਰੋਤ ਡੇਟਾ, ਟੂਲ ਨਤੀਜੇ, ਆਦਿ) ਨੂੰ ਮਾਡਲ ਇੰਟਰੈਕਸ਼ਨ ਵਿੱਚ ਸ਼ਾਮਲ ਕਰਦਾ ਹੈ। ਮਾਡਲ ਇਸ ਜਾਣਕਾਰੀ ਨੂੰ ਵਰਤ ਕੇ ਇੱਕ ਪੂਰਨ ਅਤੇ ਸੰਦਰਭਿਕ ਤੌਰ 'ਤੇ ਢੁਕਵਾਂ ਜਵਾਬ ਤਿਆਰ ਕਰਦਾ ਹੈ।

- **ਨਤੀਜਾ ਪੇਸ਼ ਕਰਨਾ**  
  ਹੋਸਟ ਕਲਾਇੰਟ ਤੋਂ ਅੰਤਿਮ ਨਤੀਜਾ ਪ੍ਰਾਪਤ ਕਰਦਾ ਹੈ ਅਤੇ ਉਪਭੋਗਤਾ ਨੂੰ ਪੇਸ਼ ਕਰਦਾ ਹੈ

**ਅਸਵੀਕਾਰੋਪਣ**:  
ਇਸ ਦਸਤਾਵੇਜ਼ ਦਾ ਅਨੁਵਾਦ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀਤਾ ਲਈ ਯਤਨ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਵਿੱਚ ਰੱਖੋ ਕਿ ਆਟੋਮੈਟਿਕ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸਮਰਥਤਾਵਾਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਆਪਣੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਹੀ ਪ੍ਰਮਾਣਿਕ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਜਰੂਰੀ ਜਾਣਕਾਰੀ ਲਈ, ਪ੍ਰੋਫੈਸ਼ਨਲ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਅਸੀਂ ਇਸ ਅਨੁਵਾਦ ਦੇ ਇਸਤੇਮਾਲ ਨਾਲ ਪੈਦਾ ਹੋਣ ਵਾਲੀਆਂ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀਆਂ ਜਾਂ ਭ੍ਰਮਾਂ ਲਈ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।