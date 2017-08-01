###Mongoose操作数据库:
	var Schema = mongoose.Schema;
	var userScheMa = new Schema({ //数据属性模型：定义数据结构,无法直接操作数据库
	userid: String,
	password: String
	},{
	versionKey: false //不要版本key
	});
	var User = mongoose.model('users', userScheMa);
	