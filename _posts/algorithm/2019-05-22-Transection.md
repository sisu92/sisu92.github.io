#트랜잭션~
## 트랜잭션 -> Auto commit 풀어주고, 에러시 Rollback 처리가 될 수 있도록한다!?
~~~java
public int moveAccount(String sendAcc, String recvAcc, int amount) throws SQLException
	{
		
		//	 1. Connection 객체 생성
        Connection con = null;
		con =DriverManager.getConnection(url,user,pass);
		

		con.setAutoCommit(false);//@@ 2. Auto-commit을 해제  
        //All or NOTHIng -> Transetion 이라고 한다. 전부 하거나 전부 말거나
        

        //	 3. 출금계좌에서 이체금액을 뺀다
		String sql1 = "UPDATE  account SET amount = amount-? WHERE account_num=?";
		//	 4. 입금계좌에 이체금액을 더한다
        String sql2 ="UPDATE  account SET amount = amount+? WHERE account_num=?";
		PreparedStatement ps1 = con.prepareStatement(sql1);
		ps1.setInt(1,amount);
		ps1.setString(2,sendAcc);
		/*int rs1*/ = ps1.executeUpdate();	

        ----------
        if(re1!=1) {
			con.rollback();  //결과치를 받아서 결과가 없으면 롤백해서 이체를 막는다.
			return -1;
        -----------

		PreparedStatement ps2 = con.prepareStatement(sql2);
		ps2.setInt(1,amount);
		ps2.setString(2,recvAcc);
		ps2.executeUpdate();
		


        con.commit();   //@@ 5. commit을 전송한다
		

        
        ps1.close();   //	 6. 객체 닫기
		ps2.close();
		con.close();
		
		
		//	 - 만일 정상적인 경우는 0을 리턴하고 도중에 잘못되었으면 트랜잭션을 롤백시키고 -1을 리턴
		return 0;
	}

~~~
#화면구성 비디오샾
~~~ java

		JPanel p_east = new JPanel();  //
		p_east.setBorder(new TitledBorder("비디오 검색"));  //양쪽으로 나뉨 _right
		JPanel p_east_north = new JPanel(); //east ->north
		p_east_north.add(comVideoSearch);
		p_east_north.add(tfVideoSearch);
		
        
        
        p_east.setLayout(new BorderLayout());  //그 중에 오른쪽을 다시 하나의 틀로 
		p_east.add(new JScrollPane(tableVideo),BorderLayout.CENTER); //JTable 은 반드시 JScrollPane으로 실행?
    
       ------------------------------------------------------------------------
        JTable		tableVideo;    ->   tableVideo = new JTable(tbModelVideo);  // VIEW SCREEN ->객체 생성할 때 모델을 연결시킨다.
	    VideoTableModel tbModelVideo;  -> tbModelVideo = new VideoTableModel(); // MODEL

                class VideoTableModel extends AbstractTableModel { 
	        	ArrayList data = new ArrayList();
		        String [] columnNames = {"비디오번호","제목","장르","감독","배우"};
		--------------------------------------------------------------------------
       
        p_east.add(p_east_north,BorderLayout.NORTH); //east.north 에 붙임;



setEditable(false); //편집금지
setEnabled(false); //값을 못 가지고 옴	



~~~

