EA Agent Loader
============

[![Release](https://img.shields.io/github/release/electronicarts/ea-agent-loader.svg)](https://github.com/electronicarts/ea-agent-loader/releases)
[![Maven Central](https://img.shields.io/maven-central/v/com.ea.agentloader/ea-agent-loader-parent.svg)](http://repo1.maven.org/maven2/com/ea/agentloader/)
[![Javadocs](https://img.shields.io/maven-central/v/com.ea.agentloader/ea-agent-loader.svg?label=Javadocs)](http://www.javadoc.io/doc/com.ea.agentloader/ea-agent-loader)
[![Build Status](https://img.shields.io/travis/electronicarts/ea-agent-loader.svg)](https://travis-ci.org/electronicarts/ea-agent-loader)

EA Agent Loader is a collection of utilities for [java agent](https://docs.oracle.com/javase/8/docs/api/java/lang/instrument/package-summary.html) developers.
It allows programmers to write and test their java agents using dynamic agent loading (without using the -javaagent jvm parameter).

Developer & License
======
This project was developed by [Electronic Arts](http://www.ea.com) and is licensed under the [BSD 3-Clause License](LICENSE).

Example
=======
```java
public class HelloAgentWorld
{
    public static class HelloAgent
    {
        public static void agentmain(String agentArgs, Instrumentation inst)
        {
            System.out.println(agentArgs);
            System.out.println("Hi from the agent!");
            System.out.println("I've got instrumentation!: " + inst);
        }
    }

    public static void main(String[] args)
    {
        AgentLoader.loadAgentClass(HelloAgent.class.getName(), "Hello!");
    }
}
```
