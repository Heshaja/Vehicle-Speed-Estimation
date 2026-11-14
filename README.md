
# 🚗 Vehicle Speed Estimation using YOLOv8<br/><br/>

This project detects, tracks, and estimates the speed of vehicles in a video using YOLOv8 and an IOU-based tracker.<br/><br/>

<hr/>

<b>🖼️ Frame Preview</b><br/>
<p align="center">
  <img src="Frame%20Preview.jpg" width="720"/>
</p><br/>

<hr/>

<b>⚙️ Features</b><br/>
→ Detects vehicles: <code>car</code>, <code>bus</code>, <code>truck</code>, <code>motorcycle</code><br/>
→ Estimates speed based on crossing two horizontal lines<br/>
→ Determines direction: <code>Up</code> or <code>Down</code><br/>
→ Logs results in <code>vehicle_log.csv</code><br/>
→ Saves annotated video to <code>output.avi</code><br/>
→ Saves per-frame images to <code>detected_frames/</code><br/>
→ Assigns vehicle IDs sequentially (e.g., <code>vehicle_1</code>, <code>vehicle_2</code>)<br/><br/>

<hr/>

<b>🧠 How It Works</b><br/>
→ Vehicles are detected using YOLOv8<br/>
→ IOU (Intersection over Union) is used to track objects between frames<br/>
→ When a vehicle crosses the red line, a timestamp is recorded<br/>
→ When it crosses the blue line, speed is calculated:<br/>
<code>Speed = Distance / Time</code><br/>
→ Direction is based on crossing order (Red → Blue = Down, Blue → Red = Up)<br/><br/>

<hr/>

<b>🗂️ Project Structure</b><br/>

<pre>
🎥 highway.mp4               → Input video
🎥 output.avi                → Annotated output video
📄 vehicle_log.csv           → CSV file with speed & direction logs
📄 vehicle_speed_estimation.py → Main processing script
📄 tracker.py                → IOU-based tracking class
📁 detected_frames          → Output image frames
🖼️ Frame Preview.jpg         → Visual preview (added to README)
</pre><br/>

<hr/>

<b>📋 Output CSV Format</b><br/>

Each row includes:<br/>
→ <code>Frame</code> – Frame number<br/>
→ <code>Vehicle_ID</code> – e.g., vehicle_1, vehicle_2...<br/>
→ <code>Vehicle_Type</code> – car / truck / etc.<br/>
→ <code>Direction</code> – Up / Down<br/>
→ <code>Speed_Km_h</code> – Estimated speed<br/>
→ <code>cx, cy, x1, y1, x2, y2</code> – Bounding box and center<br/><br/>

<hr/>

<b>📦 Requirements</b><br/>
→ Python 3.8+<br/>
→ Install dependencies:<br/>

<pre>
pip install ultralytics opencv-python pandas
</pre><br/>

<hr/>

<b>▶️ How to Run</b><br/>

→ Make sure <code>highway.mp4</code> and <code>yolov8s.pt</code> are in the same folder<br/>
→ Run the script:<br/>

<pre>
python vehicle_speed_estimation.py
</pre><br/>

<hr/>

<b>📌 Notes:</b><br/>
→ You can change the distance between lines in the code (default = 20m)<br/>
→ Vehicle IDs are custom and increment sequentially<br/>
→ Frames and logs are saved automatically<br/><br/>

<hr/>
=======
# Vehicle-Speed-Estimation
