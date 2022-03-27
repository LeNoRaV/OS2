Метод бисопряжённых градиентов (СЛАУ)
Вход: аргументы функции

Выход: аргументы функции

Лимит по времени: 100 c

Лимит по памяти: 512 МБ

Условие
Реализовать метод бисопряженных градиентов для решения СЛАУ с разреженной матрицей, используя технологию OpenMP: Ax = b, где A – разреженная квадратная положительно определённая матрица, x, b – плотные векторы. Требования

Программа на языке C++ должна реализовывать функцию со следующим заголовком:

void SLE_Solver_CRS_BICG(CRSMatrix & A, double * b, double eps, int max_iter, double * x, int & count);

struct CRSMatrix {  int n; // Число строк в матрице  int m; // Число столбцов в матрице  int nz; // Число ненулевых элементов в разреженной матрице  vector val; // Массив значений матрицы по строкам  vector colIndex; // Массив номеров столбцов  vector rowPtr; // Массив индексов начала строк };

Формат входа
Функция получает в аргументах следующие переменные: A – указатель на структуру CRSMatrix, в которой хранится матрица A в CRS формате размера n×n b – указатель на массив, в котором по строкам хранится столбец b размера n×1 eps – критерий остановки ||x_k - x_{k+1}|| < eps max_iter – критерий остановки: число итераций < max_iter count – число выполненных итераций алгоритмом

Формат выхода
x – указатель на массив, в который по строкам необходимо записать столбец x размера n×1 Ответ участника считается корректным, если ||Ax - b|| < ||A|| * 0.01 Ограничения на размер задачи

Размерность матрицы n <= 10000, число ненулевых элементов nz <= 10^7.

Требования к масштабируемости
Эффективность не менее 50% для всех тестов.
