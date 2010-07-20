require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "pdfkit"
    gem.summary = %Q{HTML+CSS -> PDF}
    gem.description = %Q{Uses wkhtmltopdf to create PDFs using HTML}
    gem.email = "jared@codewordstudios.com"
    gem.homepage = "http://github.com/jdpace/PDFKit"
    gem.authors = ["jdpace"]
    gem.add_development_dependency "rspec", "~> 2.0.0.beta.8"
    gem.add_development_dependency "rspec-core", "~> 2.0.0.beta.8"
    gem.add_development_dependency 'mocha'
    gem.post_install_message = <<-POST_INSTALL_MESSAGE
#{'*'*50}

Now install wkhtmltopdf binaries:
Global: sudo `which pdfkit` --install-wkhtmltopdf
or inside RVM folder: export TO=`which pdfkit | sed 's:/pdfkit:/wkhtmltopdf:'` && pdfkit --install-wkhtmltopdf
(run pdfkit --help to see more options)

#{'*'*50}
POST_INSTALL_MESSAGE
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
end

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "PDFKit #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
