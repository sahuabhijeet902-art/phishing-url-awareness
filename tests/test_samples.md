# Test Samples

## Test 1 — Normal URL

**URL:** `https://www.example.com/login`

**Expected result:** No listed warning signs found.

**Actual result:** No listed warning signs found. This does NOT prove safety.

**Status:** PASS

---

## Test 2 — IP Address + HTTP

**URL:** `http://192.0.2.10/account`

**Expected result:**
- Uses an IP address instead of a familiar domain.
- Uses HTTP.

**Actual result:**
- Uses an IP address instead of a familiar domain.
- Uses HTTP. HTTPS alone does not prove trust.

**Status:** PASS

---

## Test 3 — @ Symbol + HTTP

**URL:** `http://example.com@sample.invalid/login`

**Expected result:**
- Contains an @ symbol.
- Uses HTTP.

**Actual result:**
- Contains an @ symbol; inspect carefully.
- Uses HTTP. HTTPS alone does not prove trust.

**Status:** PASS

---

## Test 4 — Many Hostname Segments

**URL:** `https://a.b.c.d.e.example.invalid/path`

**Expected result:**
- Contains many hostname segments/subdomains.

**Actual result:**
- Contains many hostname segments/subdomains.

**Status:** PASS

---

## Test 5 — Punycode

**URL:** `https://xn--example.invalid/`

**Expected result:**
- Contains a punycode-style hostname.

**Actual result:**
- Contains a punycode-style hostname.

**Status:** PASS
