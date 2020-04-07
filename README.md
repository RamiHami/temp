select `sum` from 
(select *, sum(t1 + t2 + t3 + t4 + t5 + t6) as `sum` from
    (select coffe*
            (select costs from ingridients where name like 'Кофе') as t1
                    from recipes where name like 'cappuchino') as tm1,
            (select water*
                (select costs from ingridients where name like 'Вода') as t2
                    from recipes where name like 'cappuchino') as tm2,
            (select cups*
                (select costs from ingridients where name like 'Стаканчики') as t3
                    from recipes where name like 'cappuchino') as tm3,
            (select sticks*
                (select costs from ingridients where name like 'Размешиватели') as t4
                    from recipes where name like 'cappuchino') as tm4,
            (select sugar*
                (select costs from ingridients where name like 'Сахар') as t5
                    from recipes where name like 'cappuchino') as tm5,
            (select milk*
                (select costs from ingridients where name like 'Молоко') as t6
                    from recipes where name like 'cappuchino') as tm6) as temp;
