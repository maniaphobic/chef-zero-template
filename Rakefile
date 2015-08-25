#

task :sync_artifacts => %w{ sync_cookbooks sync_data_bags sync_roles sync_environments }

#

task :sync_cookbooks do
  system("knife cookbook upload --all")
end

#

task :sync_data_bags do
  Dir.glob("data_bags/*").map { |e| e.split('/').last }.each do |bag_name|
    system("knife data bag create #{bag_name}")
    Dir.glob("data_bags/#{bag_name}/*.json").map do |item_path|
      system("knife data bag from file #{bag_name} #{item_path}")
    end
  end
end

#

task :sync_environments do
  true
end

#

task :sync_roles do
  true
end

#
