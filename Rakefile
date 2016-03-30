def ask(question)
  begin
    STDOUT.puts "#{question} (y/n)"
    input = STDIN.gets.strip.downcase
  end until %w(y n).include?(input)
  input
end

desc 'Push to herewebuy.org'
task :deploy do
  require 'colored'

  answer = ask "Are your sure?"
  exit if answer == 'n'

  puts '=> Memorizing current branch name...'.magenta
  current_branch = `git branch | grep "*"`.gsub('*', '').strip

  puts '=> Remove gh-pages branch...'.magenta
  system 'git branch -D gh-pages'

  puts '=> Create orphan gh-pages branch...'.magenta
  system 'git checkout --orphan gh-pages'

  puts '=> Building javascript files...'.magenta
  system 'npm run build'

  puts '=> Disallow robots...'.magenta
  #File.open('robots.txt', 'w') { |file| file.write "User-agent: *\n" }

  #puts '=> Change CNAME...'.magenta
  #File.open('CNAME', 'w') { |file| file.write 'herewebuy.org' }

  puts '=> Add everything...'.magenta
  system 'git add --all'

  puts '=> Commit everything...'.magenta
  system 'git commit -m "Deploy commit"'

  puts '=> Add deploy remote...'.magenta
  system 'git remote add deploy git@github.com:ricardok/herewebuy.org.git'

  puts '=> Force push to deploy. Get some coffee, it may take some time...'.magenta
  system 'git push -f deploy gh-pages'

  puts "=> Checkout #{current_branch} branch...".magenta
  system "git checkout #{current_branch}"

  puts '=> Done. It can take up to 10 minutes for your changes to appear herewebuy.org'.yellow
end
