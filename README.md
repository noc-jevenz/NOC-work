from IPython.display import HTML, IFrame

# 1. 将您的 API 密钥替换为 YOUR_API_KEY
api_key = 'xxx'

# 2. 构建嵌入式地图 URL
location = '1600 Amphitheatre Parkway, Mountain View, CA'
zoom_level = 16
map_size = '600x300'
map_type = 'roadmap'
url = 'https://www.google.com/maps/embed/v1/place?key=%s&q=%s&zoom=%s&maptype=%s&size=%s'%(api_key,location,zoom_level,map_size,map_type)

# 3. 创建一个 IFrame 对象，将地图 URL 作为 src 参数
iframe = IFrame(url, width=map_size.split('x')[0], height=map_size.split('x')[1])

# 4. 使用 HTML 类创建一个 HTML 对象，并将 IFrame 对象嵌入其中
html = HTML('<h3>My Embedded Map</h3>')
display(html, iframe)
