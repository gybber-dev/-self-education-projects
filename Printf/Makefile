SRCS	= \
			./ft_printf.c \
			./parser/ft_parse.c \
			./parser/ft_init_obj.c \
			./processor/ft_processor.c \
			./processor/ft_int.c \
			./processor/ft_u.c \
			./processor/ft_x.c \
			./processor/ft_char.c \
			./processor/ft_s.c \
			./processor/ft_p.c \

OBJS		= ${SRCS:.c=.o}

BOBJS		= ${BONUS:.c=.o}

NAME		= libftprintf.a

CC			= gcc

RM			= rm -f

HEADER		= ft_printf.h

FLAGS		= -Wall -Wextra -Werror

.c.o:
			${CC} $(FLAGS) -c $< -o ${<:.c=.o}

$(NAME):	$(OBJS) $(HEADER) libft.a
			ar rc $(NAME) $(OBJS) ./libft/*.o
			ranlib libftprintf.a

libft.a:
			(cd ./libft/.;$(MAKE))

all:		${NAME}

do_prev:	all
			$(CC) $(FLAGS) main.c libftprintf.a -o my_printf

do:			do_prev fclean

clean:
			${RM} ${OBJS} ${BOBJS} *.out
			(cd ./libft/.;$(MAKE) clean)
			(cd ..)
		
fclean:		clean
			${RM} ${NAME} *.a
			(cd ./libft/.;$(MAKE) fclean)
			(cd ..)

re:			fclean all

.PHONY:		all clean fclean re
