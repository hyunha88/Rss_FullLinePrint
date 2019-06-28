// Jsoup를 이용한 RSS 기사 제목만 파싱하기 -> 전체 기사 제목 출력


package rss_title;

import org.jsoup.Jsoup;
import org.jsoup.nodes.Document;
import org.jsoup.nodes.Element;
import org.jsoup.select.Elements;

public class Rss_title {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		System.out.println("오늘의 뉴스");
		//String url = "https://news.google.com/rss?hl=ko&gl=KR&ceid=KR:ko";
		try {
			
			Document doc = Jsoup.connect("https://news.google.com/rss?hl=ko&gl=KR&ceid=KR:ko").get();
		//Document doc = Jsoup.connect(url).get();
		//Element news = doc.selectFirst("item title");
		//Element title = news;
		//System.out.println(title.text());
		
		Elements news = doc.select("item title"); 
		for(Element title : news) {
			System.out.println(title.text());
		}
		
	}
		catch(Exception e) {
			e.printStackTrace();
			System.out.println("데이터 가져오기 실패");
		}

}
}
