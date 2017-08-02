###Node 之 Eventproxy

####js计数器写异步:
	(function(){
		var count = 0;
		var result = {};
		
		$.get('url1', function(data){
			result.data1 = data;
			count++;
			handle();
		});
		$.get('url2', function(data){
			result.data2 = data;
			count++;
			handle();
		});
		$.get('url3', function(data){
			result.data3 = data;
			count++;
			handle();
		});

		function handle(){
			if(count === 3){
				var html = fuck(data1, data2, data3);
				render(html);
			}
		}
	})();