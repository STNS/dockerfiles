task :default => "build"

desc "build"
task "build" do
  %w(centos ubuntu).each do |o|
    %w(x86 i386).each do |a|
      sh "docker build --rm -f #{o}-#{a} -t stns:#{o}-#{a} ."
    end
  end
end

task "push" => ["build"] do
  %w(centos ubuntu).each do |o|
    %w(x86 i386).each do |a|
      sh "docker tag stns:#{o}-#{a} pyama/stns:#{o}-#{a}"
      sh "docker push  pyama/stns:#{o}-#{a}"
    end
  end
end
