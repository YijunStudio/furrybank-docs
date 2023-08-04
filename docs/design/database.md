# Database

| 通用属性            | MySQL类型  | 名称 | 允许空 | 默认值 | 备注 |
|--------------------|-----------|------|---|--------|------|
| id                 | CHAR(36)  | 唯一标识 | × | UUID               |      |
| created_timestamp  | TIMESTAMP | 创建时间 | × | CURRENT_TIMESTAMP  |      |
| modified_timestamp | TIMESTAMP | 修改时间 | × | CURRENT_TIMESTAMP  |      |

## User 用户

必填：nickname、email、password。

新增用户时，MySQL 触发器将在 `Collection` 表和 `Account` 表中新增 `id` 一致的相应记录，且目标记录的 `user_id` 字段亦为新增的用户 `id`。

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
| nickname | VARCHAR(100) |  | × |  |  |
| email | VARCHAR(100) |  | × |  |  |
| phone | VARCHAR(36) |  |  |  |  |
| gender | TINYINT(1) |  | × |  |  |
| password | VARCHAR(100) |  | × |  |  |
| status | TINYINT(1) |  | × |  |  |
| locale | CHAR(36) |  | × |  |  |

## Category 分类

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
| user_id | CHAR(36) | 所属用户ID |  | NULL |  |
| parent_id | CHAR(36) | 父记录ID |  | NULL |  |
| name | VARCHAR(100) | 名称 | × |  | 多语言代码/用户输入 |
| name_zh | VARCHAR(100) | 名称 - 中文 |  |  |  |
| name_en | VARCHAR(100) | 名称 - 英文 |  |  |  |
| status | TINYINT(1) | 状态 | × | 1 |  |
| description | VARCHAR(100) | 描述 |  | NULL |  |
| icon | VARCHAR(100) |  |  |  | Semantic-UI Icon/Emoji |

## Channel 渠道

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
| user_id | CHAR(36) | 所属用户ID |  | NULL |  |
| parent_id | CHAR(36) | 父记录ID |  | NULL |  |
| name | VARCHAR(100) | 名称 | × |  | 多语言代码/用户输入 |
| name_zh | VARCHAR(100) | 名称 - 中文 |  |  |  |
| name_en | VARCHAR(100) | 名称 - 英文 |  |  |  |
| status | TINYINT(1) | 状态 | × | 1 |  |
| description | VARCHAR(100) | 描述 |  | NULL |  |
| icon | VARCHAR(100) |  |  |  | Semantic-UI Icon/Emoji |

## Collection 账本

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
| user_id | CHAR(36) | 所属用户ID |  | NULL |  |
| parent_id | CHAR(36) | 父记录ID |  | NULL |  |
| name | VARCHAR(100) | 名称 | × |  | 多语言代码/用户输入 |
| name_zh | VARCHAR(100) | 名称 - 中文 |  |  |  |
| name_en | VARCHAR(100) | 名称 - 英文 |  |  |  |
| status | TINYINT(1) | 状态 | × | 1 |  |
| description | VARCHAR(100) | 描述 |  | NULL |  |
| currency |  |  |  |  |  |
| icon | VARCHAR(100) |  |  |  | Semantic-UI Icon/Emoji |
| cover_url |  |  |  |  |  |

## Account 账户

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
| user_id | CHAR(36) | 所属用户ID |  | NULL |  |
| parent_id | CHAR(36) | 父记录ID |  | NULL |  |
| name | VARCHAR(100) | 名称 | × |  | 多语言代码/用户输入 |
| name_zh | VARCHAR(100) | 名称 - 中文 |  |  |  |
| name_en | VARCHAR(100) | 名称 - 英文 |  |  |  |
| status | TINYINT(1) | 状态 | × | 1 |  |
| description | VARCHAR(100) | 描述 |  | NULL |  |
| currency |  |  |  |  |  |
| type |  |  |  |  |  |
| cover_url |  |  |  |  |  |

## Transaction 账目

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
| user_id | CHAR(36) | 所属用户ID | × |  |  |
| parent_id | CHAR(36) | 父记录ID |  | NULL |  |
| datetime | TIMESTAMP |  | × | CURRENT_TIMESTAMP |  |
| description | VARCHAR(100) | 描述 | × | NULL |  |
| category_id | CHAR(36) |  | × |  |  |
| collection_id | CHAR(36) |  | × |  |  |
| account_id | CHAR(36) |  | × |  |  |
| channel_id | CHAR(36) |  | × |  |  |
| amount | DECIMAL(15,2) |  | × | 0.00 |  |
| currency | CHAR(36) |  | × | CNY |  |
| type | TINYINT(1) |  | × | 0 |  |
| comment | TEXT |  |  |  |  |

## PaidPrivilege 付费权益

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
| transaction_id | CHAR(36) | 关联账目ID |  |  |  |
|  |  |  |  |  |  |

## 空表格

| 属性 | MySQL类型 | 名称 | 允许空 | 默认值 | 备注 |
|-|-|-|-|-|-|
|  |  |  |  |  |  |