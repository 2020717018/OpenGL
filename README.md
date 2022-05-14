
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Drawing;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using Tao.OpenGl;
using Tao.Platform.Windows;

namespace Ornek2020
{
    public partial class Form1 : Form
    {
     

        public Form1()
        {
            InitializeComponent();
            OpenGlControl.InitializeContexts();

            // OpenGL ilk işlemler
            Gl.glMatrixMode(Gl.GL_MODELVIEW);
            Gl.glLoadIdentity();
            Gl.glClearColor(0, 0.6f, 0, 0);
            Gl.glMatrixMode(Gl.GL_PROJECTION);         
            Gl.glOrtho(-1.0, 13.0, -5.0, 25.0, -1, 1);
            Gl.glEnable(Gl.GL_DEPTH_TEST);
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        float[][] pt = {
           new float []{6,2,0},new float []{6,10,0},
        new float []{4,14,0},new float []{2,10,0},
        new float []{2,2,0},
        };

        public void On_kisim()
        {
            Gl.glBegin(Gl.GL_POLYGON);
            Gl.glVertex3fv(pt[0]); Gl.glColor3f(1, 0, 0);
            Gl.glVertex3fv(pt[1]); Gl.glColor3f(1, 0, 0);
            Gl.glVertex3fv(pt[2]); Gl.glColor3f(1, 0, 0);
            Gl.glVertex3fv(pt[3]); Gl.glColor3f(1, 0, 0);
            Gl.glVertex3fv(pt[4]); Gl.glColor3f(1, 0, 0);
            Gl.glEnd();
        }

        float[][] pn = {
        new float []{4.5f,7,0},new float []{4.5f,2,0},
        new float []{3.5f,2,0},new float []{3.5f,7,0}

        };


        public void diktortgen_kapi()
        {
            Gl.glBegin(Gl.GL_POLYGON);
            Gl.glVertex3fv(pn[0]); Gl.glColor3f(1, 1, 0);
            Gl.glVertex3fv(pn[1]); Gl.glColor3f(1, 1, 0);
            Gl.glVertex3fv(pn[2]); Gl.glColor3f(1, 1, 0);
            Gl.glVertex3fv(pn[3]); Gl.glColor3f(1, 1, 0);
            Gl.glEnd();
        }

        float[][] pm = {
        new float []{9,12,0},new float []{7,16,0},
        new float []{4,14,0},new float []{6,10,0}
        };

        public void kiremit()
        {
            Gl.glBegin(Gl.GL_POLYGON);
            Gl.glVertex3fv(pm[0]); Gl.glColor3f(0, 0, 0);
            Gl.glVertex3fv(pm[1]); Gl.glColor3f(0, 0, 0);
            Gl.glVertex3fv(pm[2]); Gl.glColor3f(0, 0, 0);
            Gl.glVertex3fv(pm[3]); Gl.glColor3f(0, 0, 0);
            Gl.glEnd();

        }
        float[][] pf = {
        new float []{9,4,0},new float []{9,12,0},
        new float []{6,10,0},new float []{6,2,0}

        };

        public void yanlar()
        {
            Gl.glBegin(Gl.GL_POLYGON);
            Gl.glVertex3fv(pf[0]); Gl.glColor3f(0, 0, 0);
            Gl.glVertex3fv(pf[1]); Gl.glColor3f(0, 0, 0);
            Gl.glVertex3fv(pf[2]); Gl.glColor3f(0, 0, 0);
            Gl.glVertex3fv(pf[3]); Gl.glColor3f(0, 0, 0);
            Gl.glEnd();
        }

        float[][] pg = {
        new float []{7.8f,9.5f,0},new float []{7.8f,7f,0},
        new float []{6.8f,6.5f,0},new float []{6.8f,9,0},

        };

        public void penc()
        {
            Gl.glBegin(Gl.GL_POLYGON);
            Gl.glVertex3fv(pg[0]); Gl.glColor3f(1, 1, 1);
            Gl.glVertex3fv(pg[1]); Gl.glColor3f(1, 1, 1);
            Gl.glVertex3fv(pg[2]); Gl.glColor3f(1, 1, 1);
            Gl.glVertex3fv(pg[3]); Gl.glColor3f(1, 1, 10);
            Gl.glEnd();

        }


        private void MyPaint(object sender, PaintEventArgs e)
        {
            Gl.glClear(Gl.GL_COLOR_BUFFER_BIT | Gl.GL_DEPTH_BUFFER_BIT);
            Gl.glShadeModel(Gl.GL_SMOOTH);
            Gl.glPushMatrix();
            diktortgen_kapi();
            On_kisim();
            kiremit();
            penc();
            yanlar();
            Gl.glPopMatrix();
        }

        private void OpenGlControl_Load(object sender, EventArgs e)
        {

        }

        private void MyKeyDown(object sender, KeyEventArgs e)
        {
  
        }


 

        private void timerDondur_Tick(object sender, EventArgs e)
        {

        }
    }
}
