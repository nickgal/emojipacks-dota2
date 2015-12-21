require 'yaml'

task :default do
  repo = 'https://raw.githubusercontent.com/nickgal/emojipacks-dota2/master/images/'
  Dir.chdir 'images'
  images = Dir.glob '*'
  Dir.chdir '..'
  output_hash = {
    'title' => 'Dota2'
  }
  output_hash['emojis'] = images.map do |image|
    {
      'name' => image.sub('.gif','').downcase,
      'src' => "#{repo}#{image}"
    }
  end
  File.open('output/dota2.yml', 'w') do |f|
    f.write output_hash.to_yaml
  end
end
