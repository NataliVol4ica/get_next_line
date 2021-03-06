#******************************************************************************#
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: nkolosov <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2017/09/04 13:41:34 by nkolosov          #+#    #+#              #
#    Updated: 2017/09/04 14:04:44 by nkolosov         ###   ########.fr        #
#                                                                              #
#******************************************************************************#

NAME = libft.a
HEADNAMES = libft list
INCDIR = ./includes
HEADERS = $(patsubst %, $(INCDIR)/%.h, $(HEADNAMES))
PRINTFUNCS = ft_putchar \
			ft_putstr \
			ft_putendl \
			ft_putnbr \
			ft_putnbrendl \
			ft_putchar_fd \
			ft_putstr_fd \
			ft_putendl_fd \
			ft_putnbr_fd \
			ft_print_word_tab \
			ft_print_num_tab \
			ft_log
PRINTFDIR = ./printfuncs
DPRINTFUNCS = $(patsubst %, $(PRINTFDIR)/%, $(PRINTFUNCS))
STRFUNCS =	ft_strlen \
			ft_strcat \
			ft_strncat \
			ft_strlcat \
			ft_strcmp \
			ft_strncmp \
			ft_strstr \
			ft_strnstr \
			ft_strchr \
			ft_strrchr \
			ft_strclr \
			ft_strdup \
			ft_strcpy \
			ft_strncpy \
			ft_striter \
			ft_striteri \
			ft_strmap \
			ft_strmapi \
			ft_strequ \
			ft_strnequ \
			ft_strsub \
			ft_strjoin \
			ft_strsplit \
			ft_strtrim \
			ft_split_whitespaces \
			ft_strdupab
STRFDIR = ./strfuncs
DSTRFUNCS = $(patsubst %, $(STRFDIR)/%, $(STRFUNCS))
LISTFUNCS = ft_find_del \
			ft_list_to_string \
			ft_lstnew \
			ft_lstcontains \
			ft_lstdelone \
			ft_lstdel \
			ft_lstadd \
			ft_lstiter \
			ft_lstmap \
			ft_lstpushback
LISTFDIR = ./listfuncs
DLISTFUNCS = $(patsubst %, $(LISTFDIR)/%, $(LISTFUNCS))
MEMFUNCS =	ft_strnew \
			ft_strdel \
			ft_memset \
			ft_bzero \
			ft_memcpy \
			ft_memccpy \
			ft_memmove \
			ft_memchr \
			ft_memalloc \
			ft_memdel \
			ft_memcmp
MEMFDIR = ./memfuncs
DMEMFUNCS = $(patsubst %, $(MEMFDIR)/%, $(MEMFUNCS))
CALCFUNCS = ft_atoi \
			ft_itoa \
			ft_swap \
			ft_factorial \
			ft_sqrt \
			ft_isprime \
			ft_sort_word_tab \
			ft_sort_num_tab \
			ft_count_digits \
			ft_itoa_base \
			ft_abs \
			ft_dsqrt
CALCFDIR = ./calcfuncs
DCALCFUNCS = $(patsubst %, $(CALCFDIR)/%, $(CALCFUNCS))
CHARFUNCS = ft_isdigit \
			ft_isalpha \
			ft_isalnum \
			ft_isascii \
			ft_isupper \
			ft_islower \
			ft_isprint \
			ft_iswhitespace \
			ft_toupper \
			ft_tolower
CHARFDIR = ./charfuncs
DCHARFUNCS = $(patsubst %, $(CHARFDIR)/%, $(CHARFUNCS))
FILENAMES = $(DSTRFUNCS) \
			$(DPRINTFUNCS) \
			$(DLISTFUNCS) \
			$(DMEMFUNCS) \
			$(DCALCFUNCS) \
			$(DCHARFUNCS)
ODIR = ./obj
CFILES = $(patsubst %, %.c, $(FILENAMES))
OFILES = $(patsubst %, $(ODIR)/%.o, $(FILENAMES))
FLAGS = -Wall -Wextra -Werror

BLACK = '\033[0;30m'
RED = '\033[0;31m'
GREEN = '\033[0;32m'
BROWN = '\033[0;33m'
BLUE = '\033[0;34m'
PURPLE = '\033[0;35m'
CYAN = '\033[0;36m'
LGRAY = '\033[0;37m'
DGRAY = '\033[1;30m'
LRED = '\033[1;31m'
LGREEN = '\033[1;32m'
YELLOW = '\033[1;33m'
LBLUE = '\033[1;34m'
PINK = '\033[1;35m'
LCYAN = '\033[1;36m'
WHITE = '\033[1;37m'
NC = '\033[0m' # No Color

all: $(NAME)

$(NAME): $(ODIR) $(OFILES) $(HEADERS)
	@echo ${CYAN}[Compiling $(NAME)]${NC}
	@ar rc $(NAME) $(OFILES)
	@ranlib $(NAME)
	@echo ${GREEN}"[========| $(NAME) is up to date. |========]"${NC}

$(ODIR)/%.o: %.c $(HEADERS)
	gcc $(FLAGS) -o $@ -c $< -I$(INCDIR)

$(ODIR):
	@mkdir -p $(ODIR)
	@mkdir -p $(ODIR)/$(STRFDIR)
	@mkdir -p $(ODIR)/$(PRINTFDIR)
	@mkdir -p $(ODIR)/$(LISTFDIR)
	@mkdir -p $(ODIR)/$(MEMFDIR)
	@mkdir -p $(ODIR)/$(CALCFDIR)
	@mkdir -p $(ODIR)/$(CHARFDIR)

#echo ${RED}[Removing $(NAME) *.o files]${NC}
clean:	
	@/bin/rm -rf $(ODIR)

fclean: clean
	@echo ${RED}[Removing $(NAME)]${NC}
	@/bin/rm -f $(NAME)

re: fclean all
	
norm:
	@clear
	@echo ${RED}[Checking the $(NAME) NORM]${NC}
	@norminette $(CFILES) $(HEADERS)

main:
	gcc -Wall -Wextra -Werror -o e -L. -lft main.c

gitclean: clean
	find . -name "*.DS_Store*" -delete 
	find . -name "#*#" -delete
	@/bin/rm -f e

