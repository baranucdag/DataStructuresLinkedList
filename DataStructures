using System;

namespace Deneme
{
    public class Program
    {
        static void Main(string[] args)
        {
            DoublyLinkedList<Ders> doublelinkedList = new DoublyLinkedList<Ders>();
            CircularLinkedList circularLinkedList = new CircularLinkedList();
            LinkedList linkedList = new LinkedList();
            Ders ders1 = new Ders("sadsa", 1, 5, 6, "hoca1");
            Ders ders2 = new Ders("sadada", 1, 5, 6, "hoca1");
            Ders ders3 = new Ders("sadada", 1, 5, 6, "hoca1");
            Ders ders4 = new Ders("sadada", 1, 5, 6, "hoca1");

            doublelinkedList.AddNodeToEnd(ders1);
            doublelinkedList.AddNodeToEnd(ders2);
            circularLinkedList.AddNodeToEnd(ders2);
            circularLinkedList.AddNodeToEnd(ders1);
            linkedList.AddNodeFirst(ders1);

            linkedList.PrintList();
            doublelinkedList.PrintList();
            circularLinkedList.PrintList();
        }


        public class Ders
        {
            public string DersAdı { get; set; }
            public int DersKodu { get; set; }
            public int Kredi { get; set; }
            public int Akts { get; set; }
            public string HocaAdSoyad { get; set; }
            public Ders(string ad, int kod, int kredi, int akts, string adSoyad)
            {
                this.DersAdı = ad;
                this.DersKodu = kod;
                this.Kredi = kredi;
                this.Akts = akts;
                this.HocaAdSoyad = adSoyad;
            }
        }
        public class NodeSingle
        {
            public Ders data;
            public NodeSingle next;
        };

        public class LinkedList
        {
            NodeSingle head;

            public LinkedList()
            {
                head = null;
            }

            //başa node ekleme
            public void AddNodeFirst(Program.Ders ders)
            {
                NodeSingle newNode = new NodeSingle();
                newNode.data = ders;
                newNode.next = head;
                head = newNode;
            }

            //listeyi yazdırma
            public void PrintList()
            {
                NodeSingle temp = new NodeSingle();
                temp = this.head;
                if (temp != null)
                {
                    Console.Write("Liste içeriği: ");
                    while (temp != null)
                    {
                        Console.Write(temp.data + " ");
                        temp = temp.next;
                    }
                    Console.WriteLine();
                }
                else
                {
                    Console.WriteLine("Liste boş.");
                }
            }
            //ilk node'u silme
            public void DeleteFirst()
            {
                if (this.head != null)
                {

                    NodeSingle temp = this.head;

                    this.head = this.head.next;

                    temp = null;
                }
            }

            //son node'u silme
            public void DeleteLast()
            {
                if (this.head != null)
                {
                    if (this.head.next == null)
                    {
                        this.head = null;
                    }
                    else
                    {
                        NodeSingle temp = new NodeSingle();
                        temp = this.head;
                        while (temp.next.next != null)
                            temp = temp.next;
                        NodeSingle lastNode = temp.next;
                        temp.next = null;
                        lastNode = null;
                    }
                }
            }

        }





        /*--------------*/
        public class NodeCircular
        {
            public Ders data;
            public NodeCircular next;
        };

        public class CircularLinkedList
        {
            public NodeCircular head;

            public CircularLinkedList()
            {
                head = null;
            }

            //Liste sonuna eleman ekleme
            public void AddNodeToEnd(Ders ders)
            {
                NodeCircular newNode = new NodeCircular();
                newNode.data = ders;
                newNode.next = null;
                if (head == null)
                {
                    head = newNode;
                    newNode.next = head;
                }
                else
                {
                    NodeCircular temp = new NodeCircular();
                    temp = head;
                    while (temp.next != head)
                        temp = temp.next;
                    temp.next = newNode;
                    newNode.next = head;
                }
            }

            //Liste başına eleman ekleme
            public void push_front(Program.Ders ders)
            {

                NodeCircular newNode = new NodeCircular();

                newNode.data = ders;

                newNode.next = null;

                if (head == null)
                {
                    head = newNode;
                    newNode.next = head;
                }
                else
                {
                    NodeCircular temp = new NodeCircular();
                    temp = head;
                    while (temp.next != head)
                        temp = temp.next;

                    temp.next = newNode;
                    newNode.next = head;
                    head = newNode;
                }
            }

            //listeyi yazdırma
            public void PrintList()
            {
                NodeCircular temp = new NodeCircular();
                temp = this.head;
                if (temp != null)
                {
                    Console.Write("liste şunları içerir: ");
                    while (true)
                    {
                        Console.Write(temp.data.DersAdı + " ");
                        temp = temp.next;
                        if (temp == this.head)
                            break;
                    }
                    Console.WriteLine();
                }
                else
                {
                    Console.WriteLine("Liste boş.");
                }
            }

            public void SearchElement(Program.Ders ders)
            {

                NodeCircular temp = new NodeCircular();
                temp = this.head;

                int found = 0;
                int i = 0;
                if (temp != null)
                {
                    while (true)
                    {
                        i++;
                        if (temp.data.DersAdı == ders.DersAdı)
                        {
                            found++;
                            break;
                        }
                        temp = temp.next;
                        if (temp == this.head) { break; }
                    }
                    if (found == 1)
                    {
                        Console.WriteLine(ders.DersAdı + " isimli ders bu indexte bulundu = " + i + ".");
                    }
                    else
                    {
                        Console.WriteLine(ders.DersAdı + " bu elemen listede yok.");
                    }
                }
                else
                {
                    Console.WriteLine("The list is empty.");
                }
            }
        };
        public class Node
        {
            public Ders data;
            public Node next;
            public Node prev;
        };
        public class DoublyLinkedList<Ders>
        {
            Node head;

            public DoublyLinkedList()
            {
                head = null;
            }

            //Liste sonuna node ekleme
            public void AddNodeToEnd(Program.Ders newElement)
            {
                Node newNode = new Node();
                newNode.data = newElement;
                newNode.next = null;
                newNode.prev = null;
                if (head == null)
                {
                    head = newNode;
                }
                else
                {
                    Node temp = new Node();
                    temp = head;
                    while (temp.next != null)
                        temp = temp.next;
                    temp.next = newNode;
                    newNode.prev = temp;
                }
            }


            //Liste başına node ekleme
            public void AddNodeToStart(Program.Ders ders)
            {

                Node newNode = new Node();

                newNode.data = ders;

                newNode.next = null;
                newNode.prev = null;

                if (head == null)
                {
                    head = newNode;
                }
                else
                {
                    head.prev = newNode;
                    newNode.next = head;
                    head = newNode;
                }
            }

            //ilk node'u silme
            public void DeleteFirstNode()
            {
                if (this.head != null)
                {
                    Node temp = this.head;
                    this.head = this.head.next;
                    temp = null;
                    if (this.head != null)
                        this.head.prev = null;
                }
            }

            //ders adına göre arama
            public void SearchElementByLessonsName(string dersAdı)
            {
                Node temp = new Node();
                temp = this.head;
                int found = 0;
                int i = 0;

                if (temp != null)
                {
                    while (temp != null)
                    {
                        i++;
                        if (temp.data.DersAdı == dersAdı)
                        {
                            found++;
                            break;
                        }
                        temp = temp.next;
                    }
                    if (found == 1)
                    {
                        Console.WriteLine(dersAdı + " isimli ders bu indexte bulundu = " + i + ".");
                    }
                    else
                    {
                        Console.WriteLine(dersAdı + " listede bulunamadı.");
                    }
                }
                else
                {
                    Console.WriteLine("Liste boş.");
                }
            }

            //listeyi yazdırma
            public void PrintList()
            {

                Node temp = new Node();
                temp = this.head;
                if (temp != null)
                {
                    Console.Write("Liste İçeriği: ");
                    while (temp != null)
                    {
                        Console.Write(temp.data.DersAdı + " isimli ders" + "\n");
                        temp = temp.next;
                    }
                    Console.WriteLine();
                }
                else
                {

                    Console.WriteLine("Liste boş.");
                }
            }
        }
    }


}
