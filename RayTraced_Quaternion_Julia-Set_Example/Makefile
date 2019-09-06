NAME=ray_traced_julia_set

OS	=	$(shell uname -s)

ifeq ($(OS),Linux)
	LIBS	:= -lOpenCL -lOpenGL -lGLU  -lXi -lXmu -lglut
else
	LIBS	:= -framework OpenCL -framework OpenGL -framework GLUT
endif

all: $(NAME)

$(NAME): qjulia.c qjulia_kernel.cl
	gcc qjulia.c $(LIBS) -o $(NAME)

fclean : clean
	@/bin/rm -f $(NAME)

re : fclean all
