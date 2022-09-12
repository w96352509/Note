package service;
import java.io.BufferedReader;
import java.io.DataInputStream;
import java.io.FileReader;
import java.io.IOException;

// java檔名稱
public class hw1 {
  // 主程式執行 
  public static void main(String[] args) {
      // 例外處理
	  try {
      // 讀取檔案(檔案放你 input.txt 位置)
      FileReader inputStreamFile = new FileReader("C:\\Users\\vic\\git\\repositoryWebHome\\JavaWeb-20220803\\src\\main\\java\\service\\input.txt");
  	  // 讀取文件
      BufferedReader br = new BufferedReader(inputStreamFile);
      // 讀取檔案的串流文字
      String input = br.readLine();
      // 將 string 轉 int
      int start = Integer.parseInt(input);
      // 換行讀取
      input = br.readLine();
      // 將 string 轉 int
      int end = Integer.parseInt(input);
      // 換行讀取
      input = br.readLine();
      // 將 string 轉 int
      int ans = Integer.parseInt(input);
      // 關閉串流
      br.close();
      // 將訊息顯示於 console
      System.out.println("請輸入數字在" + 
          start + " 和 " + end + "之間");
      // DataInputStream :數據輸入流用於在數據輸出流
      // System.in 為鍵盤輸入
      // new 是宣告一個物件使用
      // 物件類型 名稱 = new 物件類型();
      DataInputStream in = new DataInputStream(System.in);
      // 讀取輸入的串流文字
      input = in.readLine();
      // 將 string 轉 int 
      int userinput = Integer.parseInt(input);
      // 當輸入數字不等於答案時
      while (userinput != ans) {
    	// 條件 
        if (userinput >= end || userinput <= start) {
          // 將訊息顯示於 console
          System.out.println("輸入數字不符合範圍" + start + "~" + end);
          // 將訊息顯示於 console
          System.out.println("請再次輸入");
          // 再次讀取輸入的串流文字
          input = in.readLine();
          // 將 string 轉 int
          userinput = Integer.parseInt(input);
          // 結束當前迴圈，並進入下一次迴圈(if (userinput > ans))
          continue;
        } 
        // 判斷迴圈
        if (userinput > ans) {
          // 指向新的數字
          end = userinput;
        } else {
          // 指向新的數字
          start = userinput;
        } 
        System.out.println("提示範圍 " + 
            start + " 和 " + end);
        // 再次讀取輸入的串流文字(輸入一次就要再次讀取) 
        input = in.readLine();
        // 將 string 轉 int
        userinput = Integer.parseInt(input);
      } 
      System.out.println("答對");
    } catch (IOException iOException) {}
  }
}