һ��Gifͼ���ļ������м����ļ����кϳɵģ���˴�������ļ���ʱ�򣬲�����Jpeg����Bmp�ļ���������
��Ҫ��Gif�ļ����֡����ʽ��Ȼ���ÿһ֡���д�����������ٺϳ�Gif��
  
AnimatedGifEncoder ���ʵ���ѷ�װ�� Gif.Components.dll ��,
�����ļ���Ҫ����Gif.Components.dll, ����������:
using System; 
using System.Drawing; 
using System.Drawing.Imaging; 
using Gif.Components; // AnimatedGifEncoder ��������ռ�.
  

    
// ���� Gif 
            String [] imageFilePaths = new String[]{"c:\\01.png","c:\\02.png","c:\\03.png"};    
            String outputFilePath = "c:\\test.gif";   
            AnimatedGifEncoder e = new AnimatedGifEncoder();   
            e.Start( outputFilePath );   
            e.SetDelay(500);    // �ӳټ��
            e.SetRepeat(0);  //-1:��ѭ��,0:����ѭ�� ����   
            for (int i = 0, count = imageFilePaths.Length; i < count; i++ )   
            {  
                e.AddFrame( Image.FromFile( imageFilePaths[i] ) );  
            }  
            e.Finish();  
            
            

// ��ȡ Gif   
            string outputPath = "c:\\";  
            GifDecoder gifDecoder = new GifDecoder();  
            gifDecoder.Read( "c:\\test.gif" );  1
            for ( int i = 0, count = gifDecoder.GetFrameCount(); i < count; i++ )   
            {  
                Image frame = gifDecoder.GetFrame( i ); // frame i  
                frame.Save( outputPath + Guid.NewGuid().ToString() + ".png", ImageFormat.Png );  
            }

��������PNGͼƬ,�ŵ�C�̸�Ŀ¼����.