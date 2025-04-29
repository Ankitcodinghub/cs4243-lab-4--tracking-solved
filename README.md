# cs4243-lab-4--tracking-solved
**TO GET THIS SOLUTION VISIT:** [CS4243 Lab 4- Tracking Solved](https://www.ankitcodinghub.com/product/cs4243-lab-4-tracking-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113964&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS4243 Lab 4- Tracking Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
In this lab assignment, your task is to implement mean shift and Lucas–Kanade optical flow tracking algorithms. You will implement the following tasks:

1. Mean shift tracking. (30%)

• Mean shift tracking pipeline. (25%)

• Implement IoU metric for tracking, and report your IoU for mean shift.(5%)

2. Lucas-Kanade method for optical flow and tracking. (70%)

• Basic Lucas-Kanade method (20 %)

• Iterative Lucas-Kanade method.(20%)

• Pyramid Lucas-Kanade method.(20%)

• Object tracker pipeline and your IoU result.(10%)

Part 1: Mean Shift Tracking. (30%)

Let us first do a recap for mean shift clustering algorithm: if you recall mean shift in lab2, what we wanted to do was find modes in the density function of our data in the feature space. For the algorithm, we first define a window around it and compute the centroid of the window, then we shift the center of the window to the centroid, and repeat this procedure until the centroid stops moving.

For image, points are distributed equally everywhere, but now with each point we have an associated weight w.

The weight can be calculated by histogram back projection.

1.1 Histogram Back Projection

Back projection is a way of recording how well the pixels of a given image fit the distribution of pixels in a histogram model. In our scenario, we calculate the histogram model of the feature inside roi(region of interest) of human body and then use it to find the corresponding feature in an image.

We have completed this part for you, the value in the dst array represent the probability that a pixel belongs to a body area, based on the model histogram of roi that we used.

Therefore, in this part, the only thing you need to do is to tweak the parameters for histogram masking, i.e. the threshold and channel. These decide which part of the histogram of roi will be used as the reference.

Tweak following parameters: thresh value0, thresh value1, channel.

1.2 Mean Shift for Tracking

With the weight of each pixel, you can now calculate the weighted mean of the tracking window and perform iterative updates.

Implement following function: meanShift().

Prohibited function: cv2.meanShift()

1.3 Evaluation: Intersection over Union (IoU)

Intersection over Union (IoU) is the most commonly used evaluation metirc in the object detection area. The accuracy of the object detector is defined as follows: (credit to Adrian Rosebrock) :

Implement following function: IoU().

Part 2: Lucas-Kanade Optical Flow for Tracking. (70%)

2.1 Basic Lucas-Kanade Method

2.1.1 Keypoints Detection

2.1.2: Optical Flow Computation:

Given two consecutive frames, how can we find the flow vectors for the first frame which describe how objects move between frames? To start, we make a reasonable assumption called the brightness constancy assumption: the pixel intensity of a moving point stays the same between two consecutive frames with small time difference. In other words, picking any pixel of the moving can, its brightness stays approximately the same between frames–its movement should not affect its brightness after all.

Consider pixel intensity (a.k.a.brightness) I(x, y, t) of a point (x, y) in the first frame t. Suppose that the point has moved to (x +∆x, y +∆y) after ∆t. According to the brightness constancy assumption, we can relate intensities of the point in the two frames using the following equation:

I(x, y, t) = I(x + ∆x, y + ∆y, t + ∆t)

This equation simply states that the point that we picked will have the same intensity even after it moves in space (∆x and ∆y) and between frames (∆t). From this simple assumption, we can derive what is known as the optical flow equation. For a given point for any frame, the optical flow equation is given by:

Ix(p)vx + Iy (p)vy + It(p) = 0

Here, Ix, Iy and It are partial derivatives of pixel intensity I. Meanwhile, vx and vy are flow vectors in the x− and y−direction, respectively. These are the vectors we care about! If we can solve for these two values, we will be able to describe the motion of any object between frames.

One issue with the optical flow equation is that there are two unknowns that we want to solve for (vx and vy ). This problem is known as the aperture problem. In other words, just looking an ”aperture” at one pixel at a time, it is impossible to discern the true direction of motion of the object in question.

The Lucas–Kanade method solves this problem by adding another assumption: spatial coherence. That is, that the motion of the image contents between two frames is approximately constant within a neighborhood of the point p under consideration.

Consider a neighborhood of p, N(p) = {p1, …, pn} (e.g. 3×3 window around p). Adding the spatial coherence assumption to the optical flow equation, we see that the following should be satisfied:

For every pi ∈ N(p),

Ix(pi)vx + Iy (pi)vy = −It(pi)

These equations can be written in matrix form Av = b, where

   

Ix(p1) Iy (p1) −It(p1)

Ix(p2) Iy (p2)−It(p2)

  

A =  … …  vb =  … 

  

Ix(pn) Iy (pn) −It(pn)

Implement following function: lucas kanade().

2.1.2 Keypoints Tracking

Now we can use Lucas-Kanade method to track keypoints across multiple frames. The idea is simple: compute flow vectors at keypoints in i-th frame, and add the flow vectors to the points to keep track of the points in i + 1-th frame. We have provided the function ‘track features‘ for you.

Instead of keeping these ’bad’ tracks, we would want to somehow declare some points are ’lost’ and just discard them. One simple way to is to compare the patches around tracked points in two subsequent frames. If the patch around a point is not similar to the patch around the corresponding point in the next frame, then we declare the point to be lost. Here, we are going to use mean squared error between two normalized patches as the criterion for lost tracks. You should first normalize (here normalization means standardization, i.e. Xσ−µ) each patch and then compute MSE between them.

Implement following function: compute error().

0.1 2.2 Pyramidal Lucas-Kanade Feature Tracker

2.2.1 Iterative Lucas-Kanade Method

Below is the step-by-step description of Iterative Lucas-Kanade Method:

h iT

Let p = px py be a point on frame I. g be the flow vector guessed from previous pyramid

h iT

level(initialized as zero vector). The goal is to find flow vector v = vx vy such that p +v is the corresponding point of p on the next frame J.

– Initialize flow vector:

v

– Compute spatial gradient matrix:

px+w py+w “#

G = X X I Ix(x, y)Iy (x, y)

Ix(x, y)Iy (x, y) I

x=px−w y=py−w

– for k = 1 to K

– Compute temporal difference: δIk(x, y) = I(x, y) − J(x + gx + vx, y + gy + vy ) – Compute image mismatch vector:

p

bk = k x δIk(x, y)Iy (x, y)

x=px−w y=py−w

– Compute optical flow: vk = G−1bk

– Update flow vector for next iteration: v := v + vk

– Return v

Implement following function: iterative lucas kanade().

2.2.2 Pyramidal Lucas-Kanade Method

Following is the description of pyramidal Lucas-Kanade algorithm:

Let p be a point on image I and s be the scale of pyramid representation.

– Build pyramid representations of I and J: {IL}L=0,…,Lm and {JL}L=0,…,Lm

Lm = hgxLm gyLmiT = h0 0iT

– Initialize pyramidal guess g

– for L = Lm to 0 with step of -1

– Compute location of p on IL: pL = p/sL – Let dL be the optical flow vector at level L:

dL := IterativeLucasKanade(IL, JL, pL, gL)

– Guess for next level L − 1: gL−1 = s(gL + dL)

– Return d = g0 + d0

Implement following function: pyramid lucas kanade().

Prohibited function: cv2.calcOpticalFlowPyrLK()

2.4 Lucas-Kanade Object Tracking

Hand in
