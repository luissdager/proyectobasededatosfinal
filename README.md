# proyectobasededatosfinal
proyecto final de base de datos integrantes: Luis Simanca, Leonardo Horta, Federico terrill
integrantes: luis simanca
	     leonardo horta
	     federico terrill

===== CONSULTAS sql ======
SELECT nombre FROM asignatura WHERE creditos BETWEEN 2 AND 5 // decuelve el nombre de las asignaturas que esten entre 2 y 5 creidtos incluyedno estos

SELECT nombre,creditos FROM asignatura WHERE creditos=6   // devuelve el nombre de la asignatura con mayor o mayores creditos

SELECT nombre,creditos FROM asignatura WHERE creditos=2 // devuelve el nombre de la asignatura con menor o menores creditos

SELECT SUM(creditos) FROM asignatura           // devuelve la suma de todos los creditos de las materias registradas

SELECT AVG(creditos) FROM asignatura           // devuelve la media de los creditos de las materias registradas

SELECT COUNT(*) FROM asignatura                // devuelve el numero de materias registradas

SELECT creditos FROM asignatura WHERE nombre LIKE 'Ma%'   // devuelve el numero de creditos de los nombres de las asignatiras que empiecen por"Ma" 

SELECT * FROM asignatura WHERE nombre IN ('Matematicas')  // devulve el todas las caracteristicas de las materias que se llamen matematicas 

SELECT id FROM asignatura WHERE nombre NOT IN ('Matematicas')  // devuelve el id de todas las materias que no se llamen Matematicas 

SELECT nombre FROM plan WHERE a�o BETWEEN 2003 AND 2014     // devuelve el nombre de las materias que esten entre los a�os 2015 y 2018

SELECT nombre,creditos FROM asignatura WHERE id_plan=1 AND semestre=1 // muestra nombre y creditos que esta en la asignatura mientras el id-plan sea 1 y el semestre sea 1

SELECT SUM(creditos) FROM asignatura where id_plan=1 AND semestre=1  // suma los creditos de las materias que estan en el plan1 y semestre 1
SELECT nombre, creditos FROM asignatura WHERE nombre LIKE 'investigacion%'// muestra el nombre y los creditos de las materias que se llamen investigacion
-- phpMyAdmin SQL Dump
-- version 4.8.0.1
-- https://www.phpmyadmin.net/
--
-- Servidor: 127.0.0.1
-- Tiempo de generación: 23-05-2018 a las 03:13:34
-- Versión del servidor: 10.1.32-MariaDB
-- Versión de PHP: 7.2.5

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Base de datos: `svdc`
--

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `asignatura`
--

CREATE TABLE `asignatura` (
  `id` int(11) NOT NULL,
  `nombre` varchar(100) COLLATE utf8mb4_spanish_ci NOT NULL,
  `creditos` int(20) NOT NULL,
  `semestre` int(20) NOT NULL,
  `metodologia` varchar(50) COLLATE utf8mb4_spanish_ci NOT NULL,
  `id_plan` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_spanish_ci;

--
-- Volcado de datos para la tabla `asignatura`
--

INSERT INTO `asignatura` (`id`, `nombre`, `creditos`, `semestre`, `metodologia`, `id_plan`) VALUES
(1, 'ingles 1', 4, 1, 'presencial', 1),
(2, 'matematicas 1', 5, 1, 'presencial', 1),
(3, 'expresion oral y escrita ', 6, 1, 'presencial', 1),
(4, 'informatica general 1', 4, 1, 'presencial', 1),
(5, 'economia', 4, 2, 'presencial', 1),
(6, 'ingles 2', 4, 2, 'presencial', 1),
(7, 'matematicas 2', 5, 2, 'presencial', 1),
(8, 'psicologia general y del desarrolo', 4, 2, 'presencial', 1),
(9, 'informatica general 2', 4, 2, 'presencial', 1),
(10, 'estadistica 1', 4, 3, 'presencial', 1),
(11, 'administracion de empresas', 4, 3, 'presencial', 1),
(12, 'algebra y programacion lineal', 5, 3, 'presencial', 1),
(13, 'programacion 1', 4, 3, 'presencial', 1),
(14, 'psicologia de la educacion', 4, 3, 'presencial', 1),
(15, 'estadisticas 2', 4, 4, 'presencial', 1),
(16, 'matematicas 3', 6, 4, 'presencial', 1),
(17, 'programacion 2', 2, 4, 'presencial', 1),
(18, 'sistemas contables 1', 2, 4, 'presencial', 1),
(19, 'teorias pedagogicas', 2, 4, 'presencial', 1),
(20, 'administracion y legislacion educativa', 2, 5, 'presencial', 1),
(21, 'fisica 1', 5, 5, 'presencial', 1),
(22, 'programacion 3', 3, 5, 'presencial', 1),
(23, 'sistemas contables 2', 2, 5, 'presencial', 1),
(24, 'teoria de la imagen', 2, 5, 'presencial', 1),
(25, 'didacticas de las ciencias ', 3, 6, 'presencial', 1),
(26, 'diseno grafico', 2, 6, 'presencial', 1),
(27, 'fisica 2', 5, 6, 'presencial', 1),
(28, 'programacion 4', 2, 6, 'presencial', 1),
(29, 'sistemas operativos', 2, 6, 'presencial', 1),
(30, 'analisis y diseno de sistemas I', 2, 7, 'presencial', 1),
(31, 'epistemologia', 4, 7, 'presencial', 1),
(32, 'fotografia', 2, 7, 'presencial', 1),
(33, 'guionistica', 2, 7, 'presencial', 1),
(34, 'informatica educativa', 3, 7, 'presencial', 1),
(35, 'analisis y diseno de sistemas 2', 2, 8, 'presencial', 1),
(36, 'diseno y evolucion de sofware educativo', 3, 8, 'presencial', 1),
(37, 'mantenimiento y ensamble de computadores', 2, 8, 'presencial', 1),
(38, 'metologia de la investigacion', 2, 8, 'presencial', 1),
(39, 'realizacion de audiovisuales', 2, 8, 'presencial', 1),
(40, 'asistencia y produccion 1', 5, 9, 'presencial', 1),
(41, 'realizacion de videos ', 2, 9, 'presencial', 1),
(42, 'redes y comunicaciones de datos ', 3, 9, 'presencial', 1),
(43, 'seminario 1', 2, 9, 'presencial', 1),
(44, 'trabajo de grado', 2, 10, 'presencial', 1),
(45, 'administracion de recursos informaticos', 3, 10, 'presencial', 1),
(46, 'asistencia y produccion 2', 2, 10, 'presencial', 1),
(47, 'edicion de videos', 2, 10, 'presencial', 1),
(48, 'etica', 3, 10, 'presencial', 1),
(49, 'seminario 2', 2, 10, 'presencial', 1),
(50, 'fundamentos de la mediatica', 3, 1, 'presencial', 2),
(51, 'desarrollo humano', 2, 1, 'presencial', 2),
(52, 'epistemologia de la informacion', 3, 1, 'presencial', 2),
(53, 'historia de la educacion y formacion ', 4, 1, 'presencial', 2),
(54, 'introduccion a la investigacion', 2, 1, 'presencial', 2),
(55, 'perfl de formacion y proyecto de vida ', 2, 1, 'presencial', 2),
(56, 'alfabetizacion computacional en medios', 4, 1, 'presencial', 2),
(57, 'introduccion a la logica computacional', 6, 1, 'presencial', 2),
(58, 'gramatica y lectura en ingles', 2, 1, 'presencial', 2),
(59, 'lectura compresiva y escritura', 2, 1, 'presencial', 2),
(60, 'estado del arte de los medios', 3, 2, 'presencial', 2),
(61, 'contexto escolar', 6, 2, 'presencial', 2),
(62, 'la investigacion en informatica y medios audiovisuales', 2, 2, 'presencial', 2),
(63, 'ciencia y tegnologia', 2, 2, 'presencial', 2),
(64, 'herramientas computacionales', 4, 2, 'presencial', 2),
(65, 'informacion educativa', 3, 2, 'presencial', 2),
(66, 'teoria y aquitectura de la computacion ', 6, 2, 'presencial', 2),
(67, 'construcion de texto cientificos', 2, 2, 'presencial', 2),
(68, 'lectura y escucha en ingles ', 2, 2, 'presencial', 2),
(69, 'investigacion y docencia ', 2, 3, 'presencial', 2),
(70, 'metodologia de la investigacion cuantitativa ', 2, 3, 'presencial', 2),
(71, 'pedagogia de la informatica ', 3, 3, 'presencial', 2),
(72, 'teorias, enfoques y modelos pedagogicos 1', 2, 3, 'presencial', 2),
(73, ' fundamentos de algoritmia', 6, 3, 'presencial', 2),
(74, 'herramientas computac 2', 4, 3, 'presencial', 2),
(75, 'gestion de informacion en ingles ', 2, 3, 'presencial', 2),
(76, 'interpretacion de documentos cientificos', 2, 3, 'presencial', 2),
(77, 'sintaxis y pedagogia de la comunicacion y la imagen', 3, 3, 'presencial', 2),
(78, 'produccion de la imagen fija ', 4, 4, 'presencial', 2),
(79, 'representacion y expresion con imagenes ', 3, 4, 'presencial', 2),
(80, 'etica profesional ', 2, 4, 'presencial', 2),
(81, 'metodologia de la investigacion cualitativa ', 2, 4, 'presencial', 2),
(82, 'teorias, enfoques y modelos pedagogicos 2', 6, 4, 'presencial', 2),
(83, 'cognicion y computacion ', 3, 4, 'presencial', 2),
(84, 'lenguajes de programacion ', 6, 4, 'presencial', 2),
(85, 'expresion y construccion de textos en ingles ', 2, 4, 'presencial', 2),
(86, 'interpretacion de documentos educativos', 2, 4, 'presencial', 2),
(87, 'cultura de la imagen ', 4, 5, 'presencial', 2),
(88, 'fotografia analogica y digital ', 4, 5, 'presencial', 2),
(89, 'autogestion y desarrollo profesional ', 2, 5, 'presencial', 2),
(90, 'dialogo de saberes 1', 6, 5, 'presencial', 2),
(91, 'investigacion y desarrollo ', 2, 5, 'presencial', 2),
(92, 'didactica de la informatica ', 4, 5, 'presencial', 2),
(93, 'programacion orientada a objetos ', 4, 5, 'presencial', 2),
(94, 'lectura y escritura para el desarrollo del pensamiento', 2, 5, 'presencial', 2),
(95, 'etica y estetica de la imagen ', 4, 6, 'presencial', 2),
(96, 'desarrollo humano y calidad de la educacion ', 2, 6, 'presencial', 2),
(97, 'dialogo de saberes 2', 6, 6, 'presencial', 2),
(98, 'diseno y evaluacion de software educativo ', 4, 6, 'presencial', 2),
(99, 'modelado y desarrollo de software ', 4, 6, 'presencial', 2),
(100, 'produccion de la imagen movil y animacion por computador', 4, 6, 'presencial', 2),
(101, 'discurso y argumentacion ', 2, 6, 'presencial', 2),
(102, 'aplicacion de lo audiovisual en educacion ', 4, 7, 'presencial', 2),
(103, 'realizacion audiovisual 1', 4, 7, 'presencial', 2),
(104, 'innovacion y creatividad profesional ', 2, 7, 'presencial', 2),
(105, 'historia de la pedagogia ', 6, 7, 'presencial', 2),
(106, 'tecnologia y medio ambiente ', 2, 7, 'presencial', 2),
(107, 'diseno de proyectos telematicos educativos ', 4, 7, 'presencial', 2),
(108, 'modelado y desarrollo de software 2', 4, 7, 'presencial', 2),
(109, 'lenguajes no verbales ', 2, 7, 'presencial', 2),
(110, 'didactica de las mediaciones ', 4, 8, 'presencial', 2),
(111, 'realizacion de audiovisual 2', 4, 8, 'presencial', 2),
(112, 'desarrollo sostenible ', 2, 8, 'presencial', 2),
(113, 'politicas educativas ', 6, 8, 'presencial', 2),
(114, 'auditoria de sistemas ', 4, 8, 'presencial', 2),
(115, 'configuracion y desarrollo de proyectos tecnologicos ', 2, 8, 'presencial', 2),
(116, 'planeacion y gestion de proyectos de informatica educativa', 4, 8, 'presencial', 2),
(117, 'pensamiento, lenguaje y comunicacion ', 2, 8, 'presencial', 2),
(118, 'seminario i mediatica y pedagogia de lo audiovisual ', 4, 9, 'presencial', 2),
(119, 'implementacion de proyectos 2 ', 1, 9, 'presencial', 2),
(120, 'practica profesional docente 1', 2, 9, 'presencial', 2),
(121, 'realidades sociales y educativas 1', 6, 9, 'presencial', 2),
(122, 'normas para la presentac.de proyectos e informes de investigacion', 2, 9, 'presencial', 2),
(123, 'seminario i informatica educativa ', 4, 9, 'presencial', 2),
(124, 'seminario i logica computacional ', 4, 9, 'presencial', 2),
(125, 'seminario i tecnicas y herramientas ', 4, 9, 'presencial', 2),
(126, 'seminario ii mediatica y pedagogia de lo audiovisual ', 4, 10, 'presencial', 2),
(127, 'implementacion y sustentacion de proyectos ', 2, 10, 'presencial', 2),
(128, '203146 practica profesional docente 2', 2, 10, 'presencial', 2),
(129, 'realidades sociales y educativas 2', 6, 10, 'presencial', 2),
(130, 'trabajo de grado ', 1, 10, 'presencial', 2),
(131, 'seminario ii informatica educativa', 4, 10, 'presencial', 2),
(132, 'seminario ii logica computacional ', 4, 10, 'presencial', 2),
(133, 'seminario ii tecnicas y herramientas', 4, 10, 'presencial', 2),
(134, 'aprendizaje autonomo ', 1, 1, 'presencial', 3),
(135, 'epistemologia de la tecnologia ', 2, 1, 'presencial', 3),
(136, 'historia de la educacion y la pedagogia ', 3, 1, 'presencial', 3),
(137, 'investigacion y practica pedagogica 1', 2, 1, 'presencial', 3),
(138, 'perfil de formacion y proyecto de vida ', 2, 1, 'presencial', 3),
(139, 'informatica 1', 2, 1, 'presencial', 3),
(140, 'logica y matematica computacional ', 3, 1, 'presencial', 3),
(141, 'comprension y produccion de textos 1', 2, 1, 'presencial', 3),
(142, 'teoria de la imagen ', 3, 2, 'presencial', 3),
(143, 'contexto y universidad ', 1, 2, 'presencial', 3),
(144, 'investigacion y practica pedagogica 2', 2, 2, 'presencial', 3),
(145, 'teoria enfoques y modelos pedagogicos y didacticos ', 3, 2, 'presencial', 3),
(146, 'fundamentos de programacion ', 3, 2, 'presencial', 3),
(147, 'informatica 2', 2, 2, 'presencial', 3),
(148, 'informatica y curriculo ', 3, 2, 'presencial', 3),
(149, 'comprension y produccion de textos 2', 2, 2, 'presencial', 3),
(150, 'narrativa y guionistica ', 3, 3, 'presencial', 3),
(151, 'educacion, desarrollo y calidad ', 2, 3, 'presencial', 3),
(152, 'desarrollo personal y convivencia ', 1, 3, 'presencial', 3),
(153, 'investigacion y practica pedagogica iii (investi. y doc) ', 2, 3, 'presencial', 3),
(154, 'teoria, enfoques y modelos curriculares ', 3, 3, 'presencial', 3),
(155, 'fundamentos del diseno ', 2, 3, 'presencial', 3),
(156, 'programacion orientada a objetos', 3, 3, 'presencial', 3),
(157, 'ingles basico 1', 2, 3, 'presencial', 3),
(158, 'fotografia', 2, 4, 'presencial', 3),
(159, 'deporte universitario ', 1, 4, 'presencial', 3),
(160, 'desarrollo humano ', 3, 4, 'presencial', 3),
(161, 'investigacion y practica pedagogica 4 (formulacion) ', 2, 4, 'presencial', 3),
(162, 'estructura de datos ', 3, 4, 'presencial', 3),
(163, 'pedagogia y didactica de la informatica ', 4, 4, 'presencial', 3),
(164, 'ingles basico 2', 2, 4, 'presencial', 3),
(165, 'pedagogia y didactica de los medios ', 4, 5, 'presencial', 3),
(166, 'autogestion y gerencia de la educacion ', 4, 5, 'presencial', 3),
(167, 'contexto escolar ', 3, 5, 'presencial', 3),
(168, 'investigacion y practica pedagogica 4 (diseqo) ', 2, 5, 'presencial', 3),
(169, 'produccion multimedia', 3, 5, 'presencial', 3),
(170, 'ingles basico 3', 2, 5, 'presencial', 3),
(171, 'dialogos de saberes ', 3, 6, 'presencial', 3),
(172, 'electiva de carrera 1', 2, 6, 'presencial', 3),
(173, 'investigacion y practica pedagogica vi (tecn. y met.) ', 2, 6, 'presencial', 3),
(174, 'cognicion y computacion ', 2, 6, 'presencial', 3),
(175, 'programacion multimedia ', 3, 6, 'presencial', 3),
(176, 'proyectos tecnologicos 1', 3, 6, 'presencial', 3),
(177, 'ingles basico 4', 2, 6, 'presencial', 3),
(179, 'electiva de carrera 2', 2, 7, 'presencial', 3),
(180, 'electiva libre 1', 2, 7, 'presencial', 3),
(181, 'politicas y legislacion educativa ', 3, 7, 'presencial', 3),
(182, 'proceso docente educativo 1', 2, 7, 'presencial', 3),
(183, 'diseqo de software educativo ', 3, 7, 'presencial', 3),
(184, 'proyectos tecnologicos 2', 3, 7, 'presencial', 3),
(185, 'redes y telecomunicaciones ', 3, 7, 'presencial', 3),
(186, 'realizacion audiovisual ', 4, 8, 'presencial', 3),
(187, 'electiva de profundizacion 1', 4, 8, 'presencial', 3),
(188, 'electiva libre 2', 3, 8, 'presencial', 3),
(189, 'proceso docente educativo 2', 2, 8, 'presencial', 3),
(190, 'seminario de electiva pedagogica 1', 2, 8, 'presencial', 3),
(191, 'electiva de profundizacion 2', 6, 9, 'presencial', 3),
(192, 'electiva libre 3', 2, 9, 'presencial', 3),
(193, 'seminario de electiva pedagogica 2', 2, 9, 'presencial', 3),
(194, 'trabajo de grado 1', 2, 9, 'presencial', 3),
(195, 'electiva de profundizacion 3', 6, 10, 'presencial', 3),
(196, 'electiva libre 4', 2, 10, 'presencial', 3),
(197, 'seminario de electiva pedagogica 3', 2, 10, 'presencial', 3),
(198, 'trabajo de grado 2', 2, 10, 'presencial', 3),
(199, 'epistemologia de la comunicacion ', 3, 1, 'presencial', 4),
(200, 'epistemologia de la tecnologia ', 3, 1, 'presencial', 4),
(201, 'informatica 1 ', 3, 1, 'presencial', 4),
(202, 'matematica y logica ', 4, 1, 'presencial', 4),
(203, 'comprension y produccion de textos ', 2, 1, 'presencial', 4),
(204, 'constitucion politica y derechos humanos ', 2, 1, 'presencial', 4),
(205, 'psicologia evolutiva ', 3, 1, 'presencial', 4),
(206, 'fundamentos de algoritmia ', 4, 2, 'presencial', 4),
(207, 'fundamentos de investigacion ', 2, 2, 'presencial', 4),
(208, 'teoria de la imagen ', 3, 2, 'presencial', 4),
(209, 'informatica 2', 3, 2, 'presencial', 4),
(210, 'informatica y educacion ', 3, 2, 'presencial', 4),
(211, 'introduccion a la gestion tecnologica ', 2, 2, 'presencial', 4),
(212, 'psicologia del aprendizaje ', 3, 2, 'presencial', 4),
(213, 'educacion tecnologica ', 3, 3, 'presencial', 4),
(214, 'estadistica para investigacion educativa ', 2, 3, 'presencial', 4),
(215, 'fundamentos de programacion ', 4, 3, 'presencial', 4),
(216, 'liderazgo y emprendimiento tecnologico ', 2, 3, 'presencial', 4),
(217, 'ingles 1', 2, 3, 'presencial', 4),
(218, 'historia y epistemologia de la pedagogia ', 3, 3, 'presencial', 4),
(219, 'fundamento de diseno ', 3, 3, 'presencial', 4),
(220, 'educacion , desarrollo tecnologico y calidad ', 2, 4, 'presencial', 4),
(221, 'fotografia', 3, 4, 'presencial', 4),
(222, 'investigacion edcuativa i ( metodologia de la investigacion cuantitativa', 2, 4, 'presencial', 4),
(223, 'narrativa y guionistica ', 3, 4, 'presencial', 4),
(224, 'tecnica avanzadas de programacion ', 4, 4, 'presencial', 4),
(225, 'inglès 2', 2, 4, 'presencial', 4),
(226, 'legislacion y politica educativa ', 3, 4, 'presencial', 4),
(227, 'ambientes educativos digitales ', 4, 5, 'presencial', 4),
(228, 'bases de datos ', 4, 5, 'presencial', 4),
(229, 'gerencia de la educacion tecnologica ', 2, 5, 'presencial', 4),
(230, 'investigacion educativa 2', 2, 5, 'presencial', 4),
(231, 'produccion multimedia ', 3, 5, 'presencial', 4),
(232, 'ingles 3', 2, 5, 'presencial', 4),
(233, 'currìculo', 3, 5, 'presencial', 4),
(234, 'cognicion y computacion ', 3, 6, 'presencial', 4),
(235, 'inteligencia computacional ', 3, 6, 'presencial', 4),
(236, 'planeacion estrategica e indicadores de gestion educativa ', 3, 6, 'presencial', 4),
(237, 'practica profesional 1', 2, 6, 'presencial', 4),
(238, 'programacion web ', 4, 6, 'presencial', 4),
(239, 'realizacion audiovisual i ', 3, 6, 'presencial', 4),
(240, 'ingles 4', 2, 6, 'presencial', 4),
(241, 'didactica de la informatica ', 3, 7, 'presencial', 4),
(242, 'practica profesional 2', 2, 7, 'presencial', 4),
(243, 'proyectos tecnologicos 1', 3, 7, 'presencial', 4),
(244, 'realizacion audiovisual 2', 3, 7, 'presencial', 4),
(245, 'redes de computadores ', 4, 7, 'presencial', 4),
(246, 'electiva de carrera 1', 3, 7, 'presencial', 4),
(247, 'electiva libre 1', 2, 7, 'presencial', 4),
(248, 'diseño de software educativo ', 6, 8, 'presencial', 4),
(249, 'proyectos tecnologicos 2 ', 3, 8, 'presencial', 4),
(250, 'requisito de grado ', 2, 8, 'presencial', 4),
(251, 'electiva de carrera 3', 3, 8, 'presencial', 4),
(252, 'didactica y pedagogia de los medios ', 3, 8, 'presencial', 4),
(253, 'electiva libre 2', 2, 8, 'presencial', 4);

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `asignatura-profesores`
--

CREATE TABLE `asignatura-profesores` (
  `id` int(11) NOT NULL,
  `id_asignatura` int(11) NOT NULL,
  `id_profesor` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_spanish_ci;

--
-- Volcado de datos para la tabla `asignatura-profesores`
--

INSERT INTO `asignatura-profesores` (`id`, `id_asignatura`, `id_profesor`) VALUES
(1, 1, 1),
(2, 2, 2),
(3, 3, 3),
(4, 4, 4),
(5, 5, 5),
(6, 6, 6),
(7, 7, 7),
(8, 8, 8),
(9, 9, 9),
(10, 10, 10),
(11, 11, 11),
(12, 12, 12),
(13, 13, 13),
(14, 14, 14),
(15, 15, 15),
(16, 16, 16),
(17, 17, 17),
(18, 18, 18),
(19, 19, 19),
(20, 20, 20),
(21, 21, 21),
(22, 22, 22),
(23, 23, 23),
(24, 24, 24),
(25, 25, 25),
(26, 26, 6),
(27, 27, 3),
(28, 28, 4),
(29, 29, 10),
(30, 30, 1),
(31, 31, 3),
(32, 32, 15),
(33, 33, 3),
(34, 34, 5),
(35, 35, 6),
(36, 36, 7),
(37, 37, 1),
(38, 38, 8),
(39, 39, 10),
(40, 40, 25),
(41, 41, 22),
(42, 42, 3),
(43, 43, 23),
(44, 44, 11),
(45, 45, 6),
(46, 46, 9),
(47, 47, 7),
(48, 48, 8),
(49, 49, 1),
(50, 50, 20),
(51, 51, 1),
(52, 52, 2),
(53, 53, 3),
(54, 54, 4),
(55, 55, 5),
(56, 56, 6),
(57, 57, 7),
(58, 58, 8),
(59, 59, 9),
(60, 60, 9),
(61, 61, 1),
(62, 62, 22),
(63, 63, 4),
(64, 65, 6),
(65, 66, 7),
(66, 67, 8),
(67, 68, 9),
(68, 69, 15),
(69, 70, 16),
(70, 71, 11),
(71, 72, 12),
(72, 73, 13),
(73, 74, 14),
(74, 75, 15),
(75, 76, 6),
(76, 77, 7),
(77, 78, 18),
(78, 79, 19),
(79, 80, 20),
(80, 81, 21),
(81, 82, 22),
(82, 83, 23),
(83, 84, 24),
(84, 85, 25),
(85, 86, 1),
(86, 87, 2),
(87, 88, 3),
(88, 89, 9),
(89, 90, 10),
(90, 91, 15),
(91, 92, 12),
(92, 93, 13),
(93, 94, 14),
(94, 95, 15),
(95, 96, 13),
(96, 97, 18),
(97, 98, 3),
(98, 99, 19),
(99, 100, 10),
(100, 101, 25),
(101, 102, 1),
(102, 103, 2),
(103, 104, 3),
(104, 105, 4),
(105, 106, 5),
(106, 107, 6),
(107, 108, 7),
(108, 109, 8),
(109, 110, 9),
(110, 111, 10),
(111, 112, 11),
(112, 113, 12),
(113, 114, 13),
(114, 115, 14),
(115, 116, 15),
(116, 117, 16),
(117, 118, 17),
(118, 119, 18),
(119, 120, 19),
(120, 121, 20),
(121, 122, 21),
(122, 123, 22),
(123, 124, 23),
(124, 125, 24),
(125, 126, 25),
(126, 127, 1),
(127, 128, 2),
(128, 129, 3),
(129, 130, 4),
(130, 131, 5),
(131, 132, 6),
(132, 133, 7),
(133, 134, 8),
(134, 135, 9),
(135, 136, 10),
(136, 137, 11),
(137, 138, 12),
(138, 139, 13),
(139, 140, 14),
(140, 141, 15),
(141, 142, 16),
(142, 143, 17),
(143, 144, 18),
(144, 145, 19),
(145, 146, 20),
(146, 147, 21),
(147, 148, 22),
(148, 149, 23),
(149, 150, 24),
(150, 151, 25),
(151, 152, 1),
(152, 153, 2),
(153, 154, 3),
(154, 155, 4),
(155, 156, 5),
(156, 157, 6),
(157, 158, 7),
(158, 159, 8),
(159, 160, 9),
(160, 161, 10),
(161, 162, 11),
(162, 163, 12),
(163, 164, 13),
(164, 165, 14),
(165, 166, 15),
(166, 167, 16),
(167, 168, 17),
(168, 169, 18),
(169, 170, 19),
(170, 171, 20),
(171, 172, 21),
(172, 173, 22),
(173, 174, 23),
(174, 175, 24),
(175, 176, 25),
(176, 177, 1),
(177, 178, 2),
(178, 179, 3),
(179, 180, 4),
(180, 181, 5),
(181, 182, 6),
(182, 183, 7),
(183, 184, 8),
(184, 185, 9),
(185, 186, 10),
(186, 187, 11),
(187, 188, 12),
(188, 189, 13),
(189, 190, 14),
(190, 191, 15),
(191, 192, 16),
(192, 193, 17),
(193, 194, 18),
(194, 195, 19),
(195, 196, 20),
(196, 197, 21),
(197, 198, 22),
(198, 199, 23),
(199, 200, 24),
(200, 201, 25),
(201, 202, 1),
(202, 203, 2),
(203, 204, 3),
(204, 205, 4),
(205, 206, 5),
(206, 207, 6),
(207, 208, 7),
(208, 209, 8),
(209, 210, 9),
(210, 211, 10),
(211, 212, 11),
(212, 213, 12),
(213, 214, 13),
(214, 215, 14),
(215, 216, 15),
(216, 217, 16),
(217, 218, 17),
(218, 219, 18),
(219, 220, 19),
(220, 221, 20),
(221, 222, 21),
(222, 223, 22),
(223, 224, 23),
(224, 225, 24),
(225, 226, 25),
(226, 227, 1),
(227, 228, 2),
(228, 229, 3),
(229, 230, 4),
(230, 231, 5),
(231, 232, 6),
(232, 233, 7),
(233, 234, 8),
(234, 235, 9),
(235, 236, 10),
(236, 237, 11),
(237, 238, 12),
(238, 239, 13),
(239, 240, 14),
(240, 241, 15),
(241, 242, 16),
(242, 243, 17),
(243, 244, 18),
(244, 245, 19),
(245, 246, 20),
(246, 247, 21),
(247, 248, 22),
(248, 249, 23),
(249, 250, 24),
(250, 251, 25),
(251, 252, 3),
(252, 253, 1);

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `plan`
--

CREATE TABLE `plan` (
  `id` int(11) NOT NULL,
  `nombre` varchar(50) COLLATE utf8mb4_spanish_ci NOT NULL,
  `año` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_spanish_ci;

--
-- Volcado de datos para la tabla `plan`
--

INSERT INTO `plan` (`id`, `nombre`, `año`) VALUES
(1, 'pensum 1', 1994),
(2, 'pensum 2', 2002),
(3, 'pensum 3', 2008),
(4, 'pensum 4', 2014);

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `profesores`
--

CREATE TABLE `profesores` (
  `id` int(11) NOT NULL,
  `nombre1` varchar(50) COLLATE utf8mb4_spanish_ci NOT NULL,
  `nombre2` varchar(50) COLLATE utf8mb4_spanish_ci NOT NULL,
  `apellido1` varchar(50) COLLATE utf8mb4_spanish_ci NOT NULL,
  `apellido2` varchar(50) COLLATE utf8mb4_spanish_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_spanish_ci;

--
-- Volcado de datos para la tabla `profesores`
--

INSERT INTO `profesores` (`id`, `nombre1`, `nombre2`, `apellido1`, `apellido2`) VALUES
(1, 'manuel', 'fernando', 'caro', 'pineres'),
(2, 'adan', '', 'gomez', 'salgado'),
(3, 'miguel ', 'angel', 'palomino', 'hawasly'),
(4, 'carlos', 'mauricio', 'galeano', 'almanza'),
(5, 'linda', 'luz', 'lee', ''),
(6, 'johanna', '', 'fernández', 'meza'),
(7, 'adriana', '', 'olier', 'quiceno'),
(8, 'gloria', 'isabel', 'osorio', 'orozco'),
(9, 'lorena', '', 'reyes', 'lora'),
(10, 'jhon', 'jairo', 'puerta', 'fajardo'),
(11, 'samir', '', 'rubio', 'galvez'),
(12, 'julio', 'anival', 'villalva', 'anaya'),
(13, 'boris ', 'enrique', 'espitia', 'machado'),
(14, 'franklin', 'eduardo', 'martine', 'avila'),
(15, 'ali', '', 'culchac', 'de la vega'),
(16, 'jaime', 'luis', 'herandez', 'arteaga'),
(17, 'diana ', 'paulina', 'quintero', 'riasco'),
(18, 'raul', 'emiro', 'toscano', 'miranda'),
(19, 'alexander', '', 'toscono', 'ricardo'),
(20, 'carlos', 'andres', 'hernandez', 'doria'),
(21, 'giovanni', '', 'argel', 'fuentes'),
(22, 'carlos', 'nemesio', 'vergara', 'martinez'),
(23, 'juancri', '', 'barrera', 'navarro'),
(24, 'sandra', 'milena', 'diaz', 'ramos'),
(25, 'martha', 'cecilia', 'pacheco', 'lora'),
(26, 'julio', 'jose', 'rangel', 'vellojin'),
(27, 'huber', 'yesid', 'castro', 'escobar'),
(28, 'jaime', 'arturo ', 'correa', 'narvaez ');

--
-- Índices para tablas volcadas
--

--
-- Indices de la tabla `asignatura`
--
ALTER TABLE `asignatura`
  ADD PRIMARY KEY (`id`);

--
-- Indices de la tabla `asignatura-profesores`
--
ALTER TABLE `asignatura-profesores`
  ADD PRIMARY KEY (`id`);

--
-- Indices de la tabla `plan`
--
ALTER TABLE `plan`
  ADD PRIMARY KEY (`id`);

--
-- Indices de la tabla `profesores`
--
ALTER TABLE `profesores`
  ADD PRIMARY KEY (`id`);

--
-- AUTO_INCREMENT de las tablas volcadas
--

--
-- AUTO_INCREMENT de la tabla `asignatura`
--
ALTER TABLE `asignatura`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=254;

--
-- AUTO_INCREMENT de la tabla `asignatura-profesores`
--
ALTER TABLE `asignatura-profesores`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=253;

--
-- AUTO_INCREMENT de la tabla `plan`
--
ALTER TABLE `plan`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=5;

--
-- AUTO_INCREMENT de la tabla `profesores`
--
ALTER TABLE `profesores`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=29;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
