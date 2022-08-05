# Controlador
public interface Controlador {
    
public abstract void ligar();
public abstract void desligar();

public abstract void abrirMenu();
public abstract void fecharMenu();

public abstract void maisVolume();
public abstract void menosVolume();

public abstract void ligarMudo();
public abstract void desligarMudo();

public abstract void play();
public abstract void pause();


}

#ControleRemoto

public class ControleRemoto  implements Controlador{
    
private int volume;
private boolean ligado;
private boolean tocando;


public ControleRemoto(){

    this.volume =  50;
    this.ligado = false;
    this.tocando = false;
}

public void setVolume(int v){
this.volume = v;
}

public int getVolume(){
    return this.volume;
}

public boolean getLigado() {
    return ligado;
}

public void setLigado(boolean ligado) {
    this.ligado = ligado;
}

public boolean getTocando() {
    return tocando;
}

public void setTocando(boolean tocando) {
    this.tocando = tocando;
}

@Override
public void ligar() {
    this.setLigado(false);
    // TODO Auto-generated method stub
}

@Override
public void desligar() {

this.setLigado(false);
    // TODO Auto-generated method stub
}

@Override
public void abrirMenu() {
System.out.println("Está ligado?  " + this.getLigado());
System.out.println("Esta tocando?  "  + this.getTocando());
System.out.println("Volume: " + this.getVolume());
for( int i = 0; i <= this.getVolume(); i += 10){
    System.out.println("[]");
}  
    // TODO Auto-generated method stub
}

@Override
public void fecharMenu() {
System.out.println("fechando Menu...");
    // TODO Auto-generated method stub

}

@Override
public void maisVolume() {
    if(this.getLigado()){
        this.setVolume(this.getVolume() +5);
    }
    // TODO Auto-generated method stub
}

@Override
public void menosVolume() {
    if(this.getLigado()){
        this.setVolume(this.getVolume() -5);
    }
    // TODO Auto-generated method stub
}
@Override
public void ligarMudo() {
    if( this.getLigado() && this.getVolume() > 0){
        this.setVolume(0);
    }
    // TODO Auto-generated method stub
}

@Override
public void desligarMudo() {
    if(this.getLigado () && this.getVolume() == 0){
        this.setVolume(50);
    }
    // TODO Auto-generated method stub
}

@Override
public void play() {
    if(this.getLigado() && !(this.getTocando())){
        this.setTocando(true);
    }
    // TODO Auto-generated method stub
    
}

@Override
public void pause() {
    if(this.getLigado() && this.getTocando()){
        this.setTocando(false);
    }
    // TODO Auto-generated method stub
}

}
#Controle

public class Controle {
    
public static void main(String[] args) {
    

ControleRemoto c = new ControleRemoto();

c.ligar();
c.maisVolume();
c.abrirMenu();
c.play();
c.fecharMenu();

}


}

