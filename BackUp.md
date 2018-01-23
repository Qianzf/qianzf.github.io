
>  让JAVA代码插件化

	public static void main(String[] args) throws Exception {
		URL[] urls = new URL[1];
		urls[0] = new URL("file:///D:/puyinYunWei/operationPlatForm/web/WEB-INF/classes/extends/");
		URLClassLoader uc = URLClassLoader.newInstance(urls );
		Class<?> cla = uc.loadClass("Hello");
		// 遍历方法
		for (Method me : cla.getMethods()) {
			// System.out.println(me.getName());
			if (me.getName().equals("install") && me.getParameterTypes().length == 0) {
				System.out.println(me.getParameterTypes().length);
				me.invoke(cla.newInstance());
			}
		}
	}
