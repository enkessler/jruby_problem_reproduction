require 'open3'

def run_command(command)
  # This way works fine
  # system(command)

  # This way errors
  Open3.popen3(command) do |_stdin, stdout, _stderr, _thread|
    while line = stdout.gets do
      # Continue to pass along output to whatever process is running this task
      puts(line)
    end
  end
end

task 'task_1' do
  puts 'Doing a thing!'
end

task :default do
  run_command('bundle exec rake task_1')
end
