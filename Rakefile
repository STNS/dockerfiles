task :default => "build"

desc "build"
task "build" do
  %w(centos ubuntu).each do |o|
    %w(x86 i386).each do |a|
      sh "docker build --build-arg GOLANG_VERSION=1.8 --rm -f #{o}-#{a} -t pyama/stns:#{o}-#{a} ."
    end
  end
end

task "push" => ["build"] do
  %w(centos ubuntu).each do |o|
    %w(x86 i386).each do |a|
      sh "docker push  pyama/stns:#{o}-#{a}"
    end
  end
end
