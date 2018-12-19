# rails-in-one-page
Cheat sheet
## Counter cache

student.rb

    class student < ActiveRecord::Base
      belongs_to :klass, counter_cache: true

klass.rb

    class klass < ActiveRecord::Base
      has_many :students


migration file
    
    def change
        add_column :klass, :students_count, default: 0
        Klass.find_each { |k| Klass.reset_counters(k.id, :students) }
    end    
