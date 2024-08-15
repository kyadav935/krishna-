import 'package:flutter/material.dart';

class HomeScreen extends StatelessWidget {
  Widget singleProduct(String imageUrl) {
    return Container(
      margin: EdgeInsets.symmetric(horizontal: 5),
      height: 230,
      width: 160,
      decoration: BoxDecoration(
        color: Color(0xffd9dad9),
        borderRadius: BorderRadius.circular(10),
      ),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Expanded(
            flex: 2,
            child: Image.network(
              imageUrl,
              fit: BoxFit.cover,
            ),
          ),
          Expanded(
            child: Padding(
              padding: const EdgeInsets.symmetric(horizontal: 10, vertical: 5),
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  Text(
                    'Forest Images',
                    style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(height: 5),
                  Row(
                    children: [
                      Expanded(
                        child: Container(
                          padding: EdgeInsets.only(left: 5),
                          height: 30,
                          decoration: BoxDecoration(
                            color: Colors.grey,
                            borderRadius: BorderRadius.circular(10),
                          ),
                          child: Row(
                            children: [
                              Text(
                                '1 million',
                                style: TextStyle(fontSize: 10),
                              ),
                              Spacer(),
                              Icon(
                                Icons.arrow_drop_down,
                                size: 20,
                                color: Colors.yellow,
                              ),
                            ],
                          ),
                        ),
                      ),
                      SizedBox(width: 5),
                      Expanded(
                        child: Container(
                          height: 30,
                          decoration: BoxDecoration(
                            color: Colors.grey,
                            border: Border.all(),
                            borderRadius: BorderRadius.circular(8),
                          ),
                          child: Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            children: [
                              Icon(
                                Icons.remove,
                                size: 15,
                                color: Color(0xffd0b84c),
                              ),
                              SizedBox(width: 5),
                              Text(
                                '1',
                                style: TextStyle(
                                  color: Color(0xffd0b84c),
                                  fontWeight: FontWeight.bold,
                                ),
                              ),
                              SizedBox(width: 5),
                              Icon(
                                Icons.add,
                                size: 15,
                                color: Color(0xffd0b84c),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ],
                  ),
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Color(0xffcbcbcb),
      drawer: Drawer(),
      appBar: AppBar(
        iconTheme: IconThemeData(color: Colors.black),
        title: Text(
          'Home',
          style: TextStyle(color: Colors.black, fontSize: 17),
        ),
        actions: [
          CircleAvatar(
            radius: 12,
            backgroundColor: Color(0xffd4d181),
            child: Icon(Icons.search, size: 17, color: Colors.black),
          ),
          Padding(
            padding: const EdgeInsets.symmetric(horizontal: 5),
            child: CircleAvatar(
              backgroundColor: Color(0xffd4d181),
              radius: 12,
              child: Icon(Icons.shop, size: 17, color: Colors.black),
            ),
          ),
        ],
        backgroundColor: Color(0xffd6b738),
      ),
      body: Padding(
        padding: const EdgeInsets.symmetric(vertical: 10, horizontal: 10),
        child: Column(
          children: [
            Padding(
              padding: const EdgeInsets.symmetric(vertical: 5),
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceBetween,
                children: [
                  Text('Discover Stunning Forest Images & Photos '),
                  Text(
                    'View All',
                    style: TextStyle(color: Colors.grey),
                  ),
                ],
              ),
            ),
            SingleChildScrollView(
              scrollDirection: Axis.horizontal,
              child: Row(
                children: [
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2021/04/10/12/28/forest-6167130_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2020/04/10/21/38/forest-5024548_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2020/11/29/17/21/forest-5839450_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2020/11/29/17/20/forest-5839448_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2020/11/29/17/20/forest-5839447_640.jpg'),
                ],
              ),
            ),
            Padding(
              padding: const EdgeInsets.symmetric(vertical: 5),
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceBetween,
                children: [
                  Text('Images Views'),
                  Text(
                    'View All',
                    style: TextStyle(color: Colors.grey),
                  ),
                ],
              ),
            ),
            SingleChildScrollView(
              scrollDirection: Axis.horizontal,
              child: Row(
                children: [
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2017/01/20/00/30/mountains-1991196_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2015/12/01/20/28/road-1072823_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2015/03/26/09/54/hot-air-balloon-690293_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2013/07/18/20/27/hopetoun-falls-165617_640.jpg'),
                  singleProduct(
                      'https://cdn.pixabay.com/photo/2014/12/15/17/16/lake-569873_640.jpg'),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}

