# Portfolio2
manu.dart
import 'package:flutter/material.dart';
import 'package:thirdapp/Indro.dart';
import 'package:thirdapp/a1.dart';
import 'package:thirdapp/project.dart';

void main() {
  runApp(
    MaterialApp(
      debugShowCheckedModeBanner: false,
      initialRoute: 'home',
      routes: {
        'home': (context) => MyHome(),
        'about': (context) => MyAbout(),
        'project': (context) => MyProject(),
      },
    ),
  );
}

Indro.dart                                                                    HomePage
import 'package:flutter/material.dart';
import 'package:sliding_sheet/sliding_sheet.dart';

myAchive(num, type) {
  return Row(
    children: [
      Text(
        num,
        style: TextStyle(fontSize: 30, fontWeight: FontWeight.bold),
      ),
      Container(margin: EdgeInsets.only(top: 10), child: Text(type))
    ],
  );
}

mySpace(icon, name) {
  return Container(
    width: 105,
    height: 115,
    child: Card(
      color: Color(0xff252525),
      shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(20)),
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          Icon(
            icon,
            color: Colors.white,
          ),
          Text(
            name,
            style: TextStyle(color: Colors.white, fontSize: 20),
          )
        ],
      ),
    ),
  );
}

class MyHome extends StatefulWidget {
  const MyHome({Key? key}) : super(key: key);

  @override
  State<MyHome> createState() => _MyHomeState();
}

class _MyHomeState extends State<MyHome> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.black,
      extendBodyBehindAppBar: true,
      appBar: AppBar(
        leading: PopupMenuButton(
          color: Colors.black,
          icon: Icon(Icons.menu),
          itemBuilder: ((context) => [
                PopupMenuItem(
                  child: TextButton(
                    onPressed: () {
                      Navigator.pushNamed(context, 'project');
                    },
                    child:
                        Text('Projects', style: TextStyle(color: Colors.white)),
                  ),
                  value: 1,
                ),
                PopupMenuItem(
                  child: TextButton(
                    onPressed: () {
                      Navigator.pushNamed(context, 'about');
                    },
                    child:
                        Text('About Me', style: TextStyle(color: Colors.white)),
                  ),
                  value: 2,
                )
              ]),
        ),
        elevation: 0.0,
        backgroundColor: Colors.transparent,
      ),
      body: SlidingSheet(
        elevation: 8,
        cornerRadius: 50,
        snapSpec: const SnapSpec(
          snappings: [0.38, 0.7, 1.0],
          positioning: SnapPositioning.relativeToAvailableSpace,
        ),
        body: Container(
          child: Stack(
            children: [
              Container(
                margin: EdgeInsets.only(top: 40),
                child: Image.asset(
                  'lib/asset/a5.jpg',
                  fit: BoxFit.cover,
                  height: 300,
                  width: 400,
                ),
              ),
              Container(
                alignment: Alignment.center,
                margin: EdgeInsets.only(
                    top: MediaQuery.of(context).size.height * 0.49),
                child: Column(
                  children: [
                    Text(
                      'Suraj Yaduvanshi',
                      style: TextStyle(fontSize: 30, color: Colors.white),
                    ),
                    Text(
                      'SoftWare Developer',
                      style: TextStyle(fontSize: 20, color: Colors.white),
                    )
                  ],
                ),
              )
            ],
          ),
        ),
        builder: (context, state) {
          return Container(
              margin: EdgeInsets.only(left: 20, right: 20, top: 20),
              height: 500,
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  Row(
                    mainAxisAlignment: MainAxisAlignment.spaceBetween,
                    children: [
                      myAchive('78', ' Project'),
                      myAchive('65', ' Client'),
                      myAchive('44', ' Message'),
                    ],
                  ),
                  SizedBox(
                    height: 30,
                  ),
                  Text(
                    'Specealization In',
                    style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(
                    height: 10,
                  ),
                  Column(
                    children: [
                      Row(
                        mainAxisAlignment: MainAxisAlignment.spaceBetween,
                        children: [
                          mySpace(Icons.android, 'Android'),
                          mySpace(Icons.android, 'Android'),
                          mySpace(Icons.android, 'Android')
                        ],
                      ),
                      SizedBox(
                        height: 10,
                      ),
                      Row(
                        mainAxisAlignment: MainAxisAlignment.spaceBetween,
                        children: [
                          mySpace(Icons.android, 'Android'),
                          mySpace(Icons.android, 'Android'),
                          mySpace(Icons.android, 'Android')
                        ],
                      ),
                      SizedBox(
                        height: 10,
                      ),
                      Row(
                        mainAxisAlignment: MainAxisAlignment.spaceBetween,
                        children: [
                          mySpace(Icons.android, 'Android'),
                          mySpace(Icons.android, 'Android'),
                          mySpace(Icons.android, 'Android')
                        ],
                      )
                    ],
                  )
                ],
              ));
        },
      ),
    );
  }
}
                                                                                      About Page
 
 import 'dart:ffi';

import 'package:flutter/material.dart';
import 'package:flutter/src/foundation/key.dart';
import 'package:flutter/src/widgets/framework.dart';
import 'package:font_awesome_flutter/font_awesome_flutter.dart';

class MyAbout extends StatefulWidget {
  const MyAbout({Key? key}) : super(key: key);

  @override
  State<MyAbout> createState() => _MyAboutState();
}

class _MyAboutState extends State<MyAbout> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.black,
      extendBodyBehindAppBar: true,
      appBar: AppBar(
        elevation: 0.0,
        backgroundColor: Colors.transparent,
      ),
      body: Container(
        child: Stack(
          children: [
            Container(
              margin: EdgeInsets.only(top: 40),
              child: Image.asset(
                'lib/asset/a4.jpg',
                fit: BoxFit.cover,
                height: 300,
                width: 400,
              ),
            ),
            Container(
              alignment: Alignment.center,
              margin: EdgeInsets.only(
                  top: MediaQuery.of(context).size.height * 0.55),
              child: Column(
                children: [
                  Text('Hello I am',
                      style: TextStyle(fontSize: 30, color: Colors.white)),
                  SizedBox(
                    height: 10,
                  ),
                  Text(
                    'Suraj Yaduvanshi',
                    style: TextStyle(fontSize: 30, color: Colors.white),
                  ),
                  SizedBox(
                    height: 10,
                  ),
                  Text(
                    'SoftWare Developer',
                    style: TextStyle(fontSize: 20, color: Colors.white),
                  ),
                  SizedBox(
                    height: 10,
                  ),
                  SizedBox(
                    width: 120,
                    child: TextButton(
                      onPressed: () {},
                      child: Text('Hire Me'),
                      style: TextButton.styleFrom(
                          backgroundColor: Colors.white, primary: Colors.blue),
                    ),
                  ),
                  SizedBox(
                    height: 10,
                  ),
                  Row(
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: [
                      IconButton(
                          onPressed: () {},
                          icon: Icon(
                            FontAwesomeIcons.instagram,
                            color: Colors.white,
                          )),
                      IconButton(
                          onPressed: () {},
                          icon: Icon(
                            FontAwesomeIcons.linkedin,
                            color: Colors.white,
                          )),
                      IconButton(
                          onPressed: () {},
                          icon: Icon(
                            FontAwesomeIcons.github,
                            color: Colors.white,
                          )),
                      IconButton(
                          onPressed: () {},
                          icon: Icon(
                            FontAwesomeIcons.twitter,
                            color: Colors.white,
                          )),
                      IconButton(
                          onPressed: () {},
                          icon: Icon(
                            FontAwesomeIcons.facebook,
                            color: Colors.white,
                          )),
                    ],
                  )
                ],
              ),
            )
          ],
        ),
      ),
    );
  }
}
                                            
                                              
                                                      Project Page


import 'package:flutter/material.dart';
import 'package:flutter/src/foundation/key.dart';
import 'package:flutter/src/widgets/framework.dart';
import 'package:font_awesome_flutter/font_awesome_flutter.dart';
import 'package:thirdapp/main.dart';

class MyProject extends StatefulWidget {
  const MyProject({Key? key}) : super(key: key);

  @override
  State<MyProject> createState() => _MyProjectState();
}

class _MyProjectState extends State<MyProject> {
  myPro(lang, title, descrip, start) {
    return Container(
      height: 220,
      width: MediaQuery.of(context).size.width * 0.9,
      child: Card(
          color: Color(0xff252525),
          child: Container(
            margin: EdgeInsets.only(left: 20, right: 20, top: 30),
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(
                  lang,
                  style: TextStyle(fontSize: 18, color: Colors.white),
                ),
                SizedBox(
                  height: 20,
                ),
                Text(
                  title,
                  style: TextStyle(fontSize: 30, color: Colors.white),
                ),
                SizedBox(
                  height: 3,
                ),
                Text(
                  descrip,
                  style: TextStyle(color: Colors.white),
                ),
                SizedBox(
                  height: 20,
                ),
                Row(
                  children: [
                    Icon(
                      Icons.star,
                      color: Colors.white70,
                      size: 18,
                    ),
                    Text(
                      start,
                      style: TextStyle(color: Colors.white70),
                    ),
                    Expanded(child: Container()),
                    IconButton(
                        onPressed: () {},
                        icon: Icon(
                          FontAwesomeIcons.github,
                          color: Colors.white70,
                        ))
                  ],
                )
              ],
            ),
          )),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.black,
      appBar: AppBar(
        backgroundColor: Color(0xff252525),
        title: Text('Project'),
      ),
      body: SingleChildScrollView(
        child: Container(
          alignment: Alignment.center,
          child:
              Column(crossAxisAlignment: CrossAxisAlignment.center, children: [
            myPro('FLUTTER', 'Click 20 Code', 'An a Online Computer', '10'),
            myPro('FLUTTER', 'Click 20 Code', 'An a Online Computer', '10'),
            myPro('FLUTTER', 'Click 20 Code', 'An a Online Computer', '10'),
            myPro('FLUTTER', 'Click 20 Code', 'An a Online Computer', '10'),
            myPro('FLUTTER', 'Click 20 Code', 'An a Online Computer', '10')
          ]),
        ),
      ),
    );
  }
}

