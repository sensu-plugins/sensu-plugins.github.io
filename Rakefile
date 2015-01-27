task :generate_site do
  require 'pandoc-ruby'
  PandocRuby.allow_file_paths = true

  Dir.glob('markdown/*.md').each do |md_file|
    clean_file = File.basename(md_file, File.extname(md_file))
    File.open("#{ clean_file }.html", 'w') do |cf|
      cf.puts PandocRuby.markdown(md_file).to_html
    end
  end
end

task default: :generate_site
