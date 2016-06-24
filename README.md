# command
role explain
https://github.com/RolifyCommunity/rolify/wiki/Usage

#restore database 
pg_restore --verbose --clean --no-acl --no-owner -h localhost -d mydb latest.dump

#Product tags code
Product.all.each do |x|
product= Product.find(x.id)
	product.categories.each do |y|
product.search_tags = [] << product.name << product.brand.name << y.name
product.save
end
end
