require "rubygems"
require "stringex"

def get_input(message)
	print message
	STDIN.gets.chomp
end

desc "Create a new post"
task :new_post do
	title = get_input("Enter post title: ")
	filename = "./_posts/#{Time.now.strftime('%Y-%m-%d')}-#{title.to_url}.mardown"
	unless File.exists?(filename)
		puts "Creating new post ...#{filename}"
		open(filename, "w") do |post|
			post.puts "---"
			post.puts "layout: post"
			post.puts "title: #{title}"
			post.puts "date: #{Time.now.strftime('%Y-%m-%d %H:%M')}"
			post.puts "--"
		end
	end
end
