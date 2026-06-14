# skill-pool

Bộ sưu tập Agent Skills dùng chung, cài đặt vào project khác qua [`npx skills`](https://github.com/vercel-labs/skills).

## Cài đặt

Liệt kê các skill có trong repo:

```bash
npx skills add kuan-G/skill-pool --list
```

Cài tất cả skill:

```bash
npx skills add kuan-G/skill-pool --all
```

Cài một skill cụ thể:

```bash
npx skills add kuan-G/skill-pool --skill high-end-visual-design
```

Cài cho một agent cụ thể (ví dụ Claude Code):

```bash
npx skills add kuan-G/skill-pool -a claude-code
```

> Repo phải ở chế độ **public** trên GitHub để `npx skills` truy cập được mà không cần xác thực.

## Cấu trúc

`npx skills` quét skill theo layout `skills/<name>/SKILL.md`. Mỗi `SKILL.md` cần YAML frontmatter với hai trường bắt buộc `name` và `description`.

```
skills/
└── high-end-visual-design/
    └── SKILL.md
```

## Danh sách skill

| Skill | Mô tả |
|-------|-------|
| `high-end-visual-design` | Hướng dẫn AI thiết kế UI/UX ở đẳng cấp agency cao cấp (fonts, spacing, shadows, motion) và chặn các default khiến thiết kế trông rẻ tiền. |
