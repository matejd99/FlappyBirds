
# FlappyBirds
1.0 Опис на апликацијата
Апликацијата која ја развивав за целта на проектот е имплементација на Flappy Bird, самата игра е едноставно имплементирана и е прилично лесна за користење.

2.0 Упатство за користењ
  2.1 Почетно мени
    Првата работа која ќе ја види корисникот е почетното мени, на почетното мени има зададно четири опции кои водат до соодветно прозорче(Start, ScoreBoard, Controls, Exit).
   ![ssssdfdf](https://user-images.githubusercontent.com/79231048/131213416-897fe1d2-ff43-4841-a280-fb258fe8b276.PNG)
  2.2 Start 
    Со кликнување на копчето Start започнува самата игра, правилата се доста едноставни, корисникот треба да ги избегнува цевките кои надоаѓаат со движење на карактерот горе доле     и да не ги допре горниот и долниот дел од пејсажот. Движењата се прават со притискање на "Space" копчето со кое карактерот се движи нагоре а за паѓањето надолу е                   имплементирана гравитација со користење на тајмер со секое изминувње на тајмерот вредноста на гравитацијата се намалува за 5, а со притискање на "Space" копчето истата се 
    зголемува за 5. Иницијалната вредност на истата е 8.
    

     private void gameTimerEvent(object sender, EventArgs e)
        {
            Bird.Top += gravity;
            PipeDown.Left -= pipeSpeed;
            pipeUp.Left -= pipeSpeed;

            if (PipeDown.Left < -80)
            {
                PipeDown.Left = 800;
                score++;
                Score.Text = "Score: " + score.ToString();
            }
            if (pipeUp.Left < -110)
            {
                pipeUp.Left = 950;
                score++;
                Score.Text = "Score: " + score.ToString();
            }
        }
        
        private void gameKeyIsDown(object sender, KeyEventArgs e)
        {
            if (e.KeyCode == Keys.Space) {
                gravity = -5;
            }
        }

        private void gameKeyIsUp(object sender, KeyEventArgs e)
        {
            if (e.KeyCode == Keys.Space)
            {
                gravity = 5;
            }
        }
   
   Со цел завршување на играта имплеметиран е метод EndGame кој се повикува при прекршување на едно од правилата(Допир со рабовите од играта или цевка), истиот ја запира целата
   игра и на екранот ги дава освоените поени од соодветното ниво.
   
   2.3 Controls
    Тука е имплементирана кратка форма во која на едноставен и јасен начин се објаснети правилата и контролите за играње.
    ![contr](https://user-images.githubusercontent.com/79231048/131213559-8d3fb61f-1914-4bf9-b2e8-edefb8a185ae.PNG)
   2.4 ScoreBoard
   
   2.5 Exit
    Претставува едноставно копче за излегување од апликацијата.
