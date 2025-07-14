Great question! The `find` command is very powerful and flexible — it can filter files based on **size**, **owner**, **group**, and **permissions**.

Here's how to **use `-size`, `-user`, `-group`, and `-perm`** in `find`, with support for **MB, GB**, and other file size units.

---

## 🔢 **1. Size Filtering with `-size`**

The `-size` flag allows filtering by file size using different **suffixes**:

### 📏 Size Units in `find`

| Unit | Meaning         |
| ---- | --------------- |
| `c`  | Bytes           |
| `k`  | Kilobytes       |
| `M`  | Megabytes       |
| `G`  | Gigabytes       |
| `b`  | 512-byte blocks |

### ✅ Examples:

#### Files **exactly** 10 MB:

```bash
find . -type f -size 10M
```

#### Files **larger** than 100 MB:

```bash
find . -type f -size +100M
```

#### Files **smaller** than 1 GB:

```bash
find . -type f -size -1G
```

---

## 👤 **2. Find by Owner**

```bash
find . -user alice
```

* Finds files **owned by user `alice`**

---

## 👥 **3. Find by Group**

```bash
find . -group developers
```

* Finds files owned by group `developers`

---

## 🛡️ **4. Find by Permissions**

```bash
find . -type f -perm 644
```

* Finds files with **exact** permission `644` (`rw-r--r--`)

### Use with symbolic permissions:

```bash
find . -type f -perm -u+x
```

* Finds files where the **user has execute** permission

### Special cases:

* `-perm 777` → Exactly `rwxrwxrwx`
* `-perm -222` → At least writable by someone
* `-perm /222` → Writable by **user OR group OR others**

---

## 🧪 Combine Conditions

### Example: Find all `.log` files >50MB owned by user `bob`:

```bash
find /var/log -type f -name "*.log" -user bob -size +50M
```

### Example: Find world-writable `.sh` scripts (security risk):

```bash
find . -type f -name "*.sh" -perm -002
```

---

## 🧠 Bonus Tip: See File Owner & Group

If you want to **see** the owner/group of found files:

```bash
find . -type f -exec ls -l {} \;
```

---

Would you like a PDF reference of this or a shell script to automate common `find` tasks?
