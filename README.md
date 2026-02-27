## users テーブル


| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | unique: true |
| password | string | NOT NULL|
| name | string | NOT NULL |
| profile| text | NOT NULL |
|occupation| text | NOT NULL |
| position | text | NOT NULL |

- has_many :prototype
- has_many :comments

## prototype テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| title    | string | NOT NULL |
| catch_copy | text | NOT NULL|
| content | text| NOT NULL |
| user | reference| NOT NULL,外部キー |

- belongs_to :user
- has_many :comments

## comments テーブル
| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| content   | text | NOT NULL |
| prototype |reference| NOT NULL,外部キー|
| user|reference| NOT NULL,外部キー |

- belongs_to :user
- belongs_to :prototype