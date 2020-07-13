
package TestFAST;


import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileOutputStream;
import java.io.FileReader;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.HashSet;
import java.util.LinkedList;
import java.util.List;
import java.util.Map;
import java.util.Set;
import java.util.Map.Entry;
import java.util.concurrent.ConcurrentHashMap;

import DBSCANpack.DBSCAN_options;
import DBSCANpack.DISC;
import DBSCANpack.Metric;
import TestRtree.Point;


public class Evaluation_sample {

	
	static String path;	
	static List<BufferedReader> br = null;
	static String[] nnames = null;
	static int iter = 0;

	static int dim = 0;
	public static void main(String[] args) {

		path = args[0];
		int pminpts = 10;
		double peps = 1;
		int window = 10000;
		int stride = 1000; 
		int Time = 1;
		dim = 2;
		
		File folder = new File(path);
		File[] listOfFiles = folder.listFiles();
		nnames = new String[listOfFiles.length];
		System.out.println("number of files: " + listOfFiles.length);
		
		
		DBSCAN_options ops = new DBSCAN_options(peps,pminpts, new Metric());
		
		for (int i = 0; i < listOfFiles.length; i++) {
			nnames[i] = listOfFiles[i].getName();
			System.out.println(nnames[i]);
		}
		
		try {

			br = new LinkedList<BufferedReader>();
			for (int i = 0; i < nnames.length; i++) {
				br.add(new BufferedReader(new FileReader(path + nnames[i])));
			}
			List<Point> all = new ArrayList<Point>();
			for (int i = 0; i <= window+stride*Time;) {
				String result;
				if ((result = getData()) != null) {					
					double x[] = new double[dim] ;
					String[] splited = result.split(",");
					x[0] = Double.parseDouble(splited[0]);
					x[1] = Double.parseDouble(splited[1]);
					Point trj = new Point(Integer.toString(i), x);
					all.add(trj);
					i++;
				}
			}
			
			

			System.out.println("--------------------------------DISC--------------------------------");
		
		
			DISC bincdbscan = new DISC(all.subList(0,window),ops, dim);
    		bincdbscan.build_mRtree();
		
    		bincdbscan.Cluster();
    		
			
			for( int i = 0 ; i < Time ; i++)
			{
				bincdbscan.Buffering(all.subList(window+i*stride,window+(i+1)*stride), all.subList(i*stride,(i+1)*stride));
				bincdbscan.collect(all.subList((i+1)*stride,window+(i+1)*stride));
			}
			
		} catch (Exception e) {
			e.printStackTrace();
		}
	}

	private static String getData() {
		String line = null;

		try {
			int x = br.size();

			line = br.get(iter % x).readLine();
			if (line != null && !line.equals("")) {
				// line = nnames[iter%x]+","+line;
			}
			else{
				if (line == null) {
					BufferedReader temp = br.get(iter % x);
					line = "";
					br.remove(iter % x);
					temp.close();
				}

				return null;
			}
		} catch(Exception e){
			e.printStackTrace();
		}
		iter++;
		return line;
	}
	
	
	
	
}
