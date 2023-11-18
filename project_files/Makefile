NAME	:=	libft.a

CC	:=	clang

DEBUG_FLAG	:=	-g

FLAGS	:=	-Wall -Wextra -Werror $(DEBUG_FLAG)

INCLUDE = -I include/

ARCL	:=	ar -crs

SRCS	:=	srcs/ft_bzero.c		\
			srcs/ft_isalpha.c	\
			srcs/ft_isalnum.c	\
			srcs/ft_isprint.c	\
			srcs/ft_isascii.c	\
			srcs/ft_memset.c		\
			srcs/ft_memcpy.c		\
			srcs/ft_memmove.c	\
			srcs/ft_strlcpy.c	\
			srcs/ft_strlcat.c	\
			srcs/ft_strchr.c		\
			srcs/ft_strrchr.c	\
			srcs/ft_tolower.c	\
			srcs/ft_toupper.c	\
			srcs/ft_strlen.c		\
			srcs/ft_memchr.c		\
			srcs/ft_calloc.c		\
			srcs/ft_memcmp.c		\
			srcs/ft_strdup.c		\
			srcs/ft_strnstr.c	\
			srcs/ft_strncmp.c	\
			srcs/ft_atoi.c		\
			srcs/ft_isdigit.c	\
			srcs/ft_strjoin.c	\
			srcs/ft_itoa.c		\
			srcs/ft_substr.c		\
			srcs/ft_strtrim.c	\
			srcs/ft_putchar_fd.c	\
			srcs/ft_putstr_fd.c	\
			srcs/ft_putendl_fd.c	\
			srcs/ft_putnbr_fd.c	\
			srcs/ft_strmapi.c	\
			srcs/ft_striteri.c	\
			srcs/ft_split.c

BSRCS	:=	srcs/ft_lstnew.c			\
			srcs/ft_lstadd_front.c	\
			srcs/ft_lstsize.c		\
			srcs/ft_lstlast.c		\
			srcs/ft_lstadd_back.c	\
			srcs/ft_lstdelone.c		\
			srcs/ft_lstclear.c		\
			srcs/ft_lstiter.c		\
			srcs/ft_lstmap.c

OBJS = $(SRCS:.c=.o)

BOBJS = $(BSRCS:.c=.o)

# COLORS ================================================================= #

RED = \033[0;91m
GREEN = \033[0;92m
YELLOW = \033[0;93m
CYAN = \033[0;96m
WHITE = \033[0;97m

# ======================================================================== #


%.o : %.c
	@$(CC) $(FLAGS) $(INCLUDE) -c $< -o $@
	@echo "$(GREEN)Compiling:$(WHITE) $<"

all: $(NAME)

$(NAME): $(OBJS)
	@$(ARCL) $(NAME) $(OBJS)
	@echo "$(YELLOW)- Library created: $(WHITE)${NAME}"
	@echo "$(YELLOW)- Compiler: $(WHITE)${CC}"
	@echo "$(YELLOW)- Flags: $(WHITE)${FLAGS}"
bonus: $(OBJS) $(BOBJS)

	@$(ARCL) $(NAME) $(OBJS) $(BOBJS)
	@echo "$(YELLOW)- Library created: $(WHITE)${NAME}"
	@echo "$(YELLOW)- Compiler: $(WHITE)${CC}"
	@echo "$(YELLOW)- Flags: $(WHITE)${FLAGS}"

clean:
	@rm -f $(OBJS) $(BOBJS)
	@echo "$(RED)All $(CYAN)$(NAME)$(RED)'s objects removed with $(WHITE)${RM} $(YELLOW)"

fclean: clean
	@rm -f $(NAME)
	@echo "$(RED)...and $(CYAN)${NAME} $(RED)has been removed"

re: fclean all

push:
	git add .
	@echo "$(RED)Adding all changes..."
	sleep 1.5
	@clear
	@echo "$(GREEN)All changes added$(NC)"
	@read -p "Enter a custom commit message (leave blank to use the default message): " message; \
	if [ -n "$$message" ]; then \
		git commit -m "$$message"; \
	else \
		git commit -m "$(shell date +'%H:%M %d-%h') update"; \
	fi
	@echo "$(YELLOW)Committing...and..."
	git push
	@echo "$(GREEN)PUSHA KEKKO!$(NC)"

.PHONY: all clean fclean re bonus push
.SILENT: