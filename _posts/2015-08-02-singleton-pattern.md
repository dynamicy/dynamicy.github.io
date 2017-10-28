---
layout: post
title: '[DesignPattern]Singleton Pattern'
date: 2015-08-02 22:50
comments: true
categories: DesignPattern, CreationalPattern

---

<h2>Problems:</h2>
to do

<h2>Definition:</h2>
to do

<h2>Idea:</h2>
to do

<h2>Application:</h2>
to do

<h2>UML:</h2>
to do

<h2>Classical Singleton:</h2>
<h4>Singleton Class</h4>
<a href="https://github.com/dynamicy/DesignPatternStudy/tree/master/CreationalDesignPattern/SingletonPattern/Java/ClassicSingleton">github</a>

<pre><code>
class Singleton {
    private static Singleton instance;
    
    /* Prevent creating new instance from other class. */
    private Singleton() {}

    /* If other memebers want to get instance, they have to use this method. */
    public static Singleton getInstance() {
        if(instance == null) {
            instance = new Singleton();
        }
        return instance;
	}
</code></pre>

<pre><code>
class Main {
    public static void main(String[] args) {
        Singleton singletonInstance1 = Singleton.getInstance();
        Singleton singletonInstance2 = Singleton.getInstance();

        if(singletonInstance1 == singletonInstance2) {
            System.out.println("They're the same instance");
        }
    }
}
</code></pre>

<h4>DoubleCheckLockSingleton</h4>
<a href="https://github.com/dynamicy/DesignPatternStudy/tree/master/CreationalDesignPattern/SingletonPattern/Java/DoubleCheckLockSingleton">github</a>

<pre><code>
public class DCLSingleton {
    // Use volatile to ensure that works on multithread.
    private volatile static DCLSingleton instance = null;

    // Make this instance can be accessed only by public method.
    private DCLSingleton() {}

    public static DCLSingleton getInstance() {
        // Only if it's the first for creating instance.
        if (instance == null) {
            // The method is synchronized on the class object.
            synchronized(DCLSingleton.class) {
                // If the instance isn't existed, create the instance.
                if(instance == null) {
                    instance = new DCLSingleton();
                }
            }
        }
        return instance;
    }
}
</code></pre>

<pre><code>public class Main {
    public static void main(String args[]) {
        DCLSingleton instance1 = DCLSingleton.getInstance();
        DCLSingleton instance2 = DCLSingleton.getInstance();

        if(instance1 == instance2) {
            System.out.println("They're the same instance");
        }
    }
}
</code></pre>

<h4>EagerlySingleton</h4>
<a href="https://github.com/dynamicy/DesignPatternStudy/tree/master/CreationalDesignPattern/SingletonPattern/Java/EagerlySingleton">github</a>

<pre><code>public class ESingleton {
    // Use static initiallizer, that will make instace created fast.
    private static ESingleton instance = new ESingleton();

    private ESingleton() {}

    // Just get the instance
    public static ESingleton getInstance() {
        return instance;
    }
}
</code></pre>

<pre><code>public class Main {
    public static void main(String[] args) {
        ESingleton singletonInstance1 = ESingleton.getInstance();
        ESingleton singletonInstance2 = ESingleton.getInstance();

        if(singletonInstance1 == singletonInstance2) {
            System.out.println("They're the same instance");
        }
    }
}
</code></pre>

<h4>SynchronizedSingleton</h4>
<a href="https://github.com/dynamicy/DesignPatternStudy/tree/master/CreationalDesignPattern/SingletonPattern/Java/SynchronizedSingleton">github</a>

<pre><code>public class SSingleton {
    private static SSingleton instance = null;
    
    private SSingleton() {}

    // Make sure that only one thread can access the instance
    synchronized static public SSingleton getInstance()  {
        if (instance == null) {
            instance = new SSingleton();
        }
        return instance;
    }
}
</code></pre>

<pre><code>public class Main {
    public static void main(String args[]) {
        SSingleton instance1 = SSingleton.getInstance(); 
        SSingleton instance2 = SSingleton.getInstance(); 

        if(instance1 == instance2) {
            System.out.println("They're the same instance");
        }
    }
}
</code></pre>