# ProtoSpaceのテーブル設計

## users テーブル

| Column    | Type   | Options     |
| --------- | ------ | ----------- |
| email     | string | not null    |
| password  | string | not null    |
| name      | string | not null    |
| profile   | text   | not null    |
| occupation| text   | not null    |
| position  | text   | not null    |

association
 has_many:prototypes
 has_many:comments

## prototypes テーブル

| Column    | Type      | Options     |
| --------- | --------- | ----------- |
| title     | string    | not null    |
| catch_copy| text      | not null    |
| concept   | text      | not null    |
| user      | references|             |

association
 belongs_to:user
 has_many:comments

## comments テーブル

| Column    | Type      | Options     |
| --------- | --------- | ----------- |
| text      | text      | not null    |
| user      | references|             |
| prototype | references|             |

association
 belongs_to:user
 belongs_to:prototypes
