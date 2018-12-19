# rails-in-one-page
Cheat sheet
## Counter cache


``` add_column :klass, :students_count, default: 0```

student.rb

    class student < ActiveRecord::Base
      belongs_to :klass, counter_cache: true

klass.rb

    class klass < ActiveRecord::Base
      has_many :students



