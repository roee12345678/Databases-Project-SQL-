# Table Structures & Details
```
-- phpMyAdmin SQL Dump
-- version 5.2.1
-- https://www.phpmyadmin.net/
--
-- Host: localhost:3306
-- Generation Time: Mar 19, 2024 at 08:06 AM
-- Server version: 5.7.41
-- PHP Version: 8.1.27

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `edensv_salon`
--

-- --------------------------------------------------------

--
-- Table structure for table `Allergic`
--

CREATE TABLE `Allergic` (
  `customer_ssn` varchar(11) NOT NULL,
  `health_certificate` tinyint(1) DEFAULT NULL,
  `allergy_type` varchar(100) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Allergic`
--

INSERT INTO `Allergic` (`customer_ssn`, `health_certificate`, `allergy_type`) VALUES
('103524599', 0, 'Dust Allergy'),
('107208618', 0, 'Latex Allergy'),
('112205133', 0, 'Latex Allergy'),
('123723403', 0, 'Latex Allergy'),
('143814089', 1, 'Food Allergy'),
('180012276', 1, 'Pet Allergy'),
('185436850', 0, 'Insect Sting Allergy'),
('221765913', 0, 'Mold Allergy'),
('236739784', 1, 'Medication Allergy'),
('244330761', 1, 'Pet Allergy'),
('265971709', 1, 'Food Allergy'),
('293027303', 0, 'Mold Allergy'),
('326017990', 0, 'Insect Sting Allergy'),
('335068216', 0, 'Insect Sting Allergy'),
('358087207', 1, 'Pollen Allergy'),
('405665656', 1, 'Pollen Allergy'),
('461324683', 1, 'Pollen Allergy'),
('499807881', 1, 'Food Allergy'),
('572570798', 0, 'Dust Allergy'),
('577601827', 1, 'Cosmetic Allergy'),
('607506150', 0, 'Dust Allergy'),
('622286126', 1, 'Mold Allergy'),
('627025907', 0, 'Insect Sting Allergy'),
('656237820', 1, 'Medication Allergy'),
('675080805', 0, 'Dust Allergy'),
('701830274', 0, 'Mold Allergy'),
('715752453', 1, 'Cosmetic Allergy'),
('719028295', 1, 'Pollen Allergy'),
('736788461', 1, 'Plant Allergy'),
('743740583', 1, 'Pet Allergy'),
('746306110', 1, 'Pollen Allergy'),
('750580920', 1, 'Plant Allergy'),
('758225875', 1, 'Pollen Allergy'),
('773321809', 1, 'Pet Allergy'),
('811790823', 1, 'Cosmetic Allergy'),
('823427114', 0, 'Plant Allergy'),
('847989489', 1, 'Medication Allergy'),
('858058860', 1, 'Plant Allergy'),
('882834297', 1, 'Cosmetic Allergy'),
('890113046', 1, 'Medication Allergy'),
('910915353', 1, 'Food Allergy'),
('914702626', 0, 'Latex Allergy'),
('934425637', 1, 'Pollen Allergy');

-- --------------------------------------------------------

--
-- Table structure for table `Contract`
--

CREATE TABLE `Contract` (
  `pharmacy_id` varchar(20) NOT NULL,
  `manufacturing_company_id` varchar(11) NOT NULL,
  `start_date` date DEFAULT NULL,
  `end_date` date DEFAULT NULL,
  `supervisor` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Contract`
--

INSERT INTO `Contract` (`pharmacy_id`, `manufacturing_company_id`, `start_date`, `end_date`, `supervisor`) VALUES
('CAREPHARM12345', 'PQR90123456', '2027-08-26', '2028-08-25', NULL),
('CAREPHARM234', 'HIJ98765432', '2025-04-02', '2026-04-01', NULL),
('CAREPHARM3456', 'STU34567890', '2026-04-03', '2027-04-02', NULL),
('CAREPHARM45678', 'RST12345678', '2026-12-27', '2027-12-26', NULL),
('CAREPHARM78901', 'OPQ78901234', '2028-04-05', '2029-04-04', NULL),
('DRUGS890123', 'OPQ34567890', '2025-06-12', '2026-06-11', NULL),
('DRUGSTORE123456', 'LMN67890123', '2028-03-09', '2029-03-08', NULL),
('DRUGSTORE567890', 'MNO89012345', '2027-07-07', '2028-07-06', NULL),
('DRUGSTORE678', 'XYZ98765432', '2024-05-15', '2025-05-14', NULL),
('DRUGSTORE89012', 'PQR23456789', '2026-03-07', '2027-03-06', NULL),
('DRUGSTORE90123', 'OPQ01234567', '2026-11-30', '2027-11-29', NULL),
('HEALTHCARE1234', 'UVW23456789', '2027-01-17', '2028-01-16', NULL),
('HEALTHCARE23456', 'RST89012345', '2028-05-20', '2029-05-19', NULL),
('HEALTHCARE567', 'LMN23456789', '2025-05-17', '2026-05-16', NULL),
('HEALTHCARE6789', 'STU01234567', '2027-09-15', '2028-09-14', NULL),
('HEALTHCARE7890', 'VWX45678901', '2026-05-18', '2027-05-17', NULL),
('HEALTHCARE901', 'DEF45678901', '2024-06-10', '2025-06-09', NULL),
('HEALTHY23456', 'GHI90123456', '2025-12-26', '2026-12-25', NULL),
('HEALTHY34567', 'YZA89012345', '2025-01-14', '2026-01-13', NULL),
('HEALTHY345678', 'GHI67890123', '2027-05-19', '2028-05-18', NULL),
('HEALTHY678901', 'HIJ89012345', '2026-09-14', '2027-09-13', NULL),
('HEALTHY890123', 'EFG45678901', '2028-01-18', '2029-01-17', NULL),
('MEDICAL123456', 'YZA56789012', '2026-06-13', '2027-06-12', NULL),
('MEDICAL234567', 'VWX12345678', '2027-10-09', '2028-10-08', NULL),
('MEDICAL45678', 'GHI23456789', '2024-07-03', '2025-07-02', NULL),
('MEDICAL456789', 'RST45678901', '2025-07-05', '2026-07-04', NULL),
('MEDICAL567890', 'XYZ34567890', '2027-02-12', '2028-02-11', NULL),
('MEDICINE1234', 'PQR10987654', '2024-10-05', '2025-10-04', NULL),
('MEDICINE78901', 'JKL01234567', '2026-01-16', '2027-01-15', NULL),
('PHARMA12345', 'ABC12345678', '2024-04-01', '2025-03-31', NULL),
('PHARMA234567', 'MNO12345678', '2026-02-11', '2027-02-10', NULL),
('PHARMA2345678', 'LMN90123456', '2026-10-08', '2027-10-07', NULL),
('PHARMA456789', 'HIJ56789012', '2028-02-13', '2029-02-12', NULL),
('PHARMA901234', 'JKL78901234', '2027-06-14', '2028-06-13', NULL),
('PHARMACY7890', 'MNO54321098', '2024-09-11', '2025-09-10', NULL),
('PILLS456789', 'XYZ67890123', '2025-09-13', '2026-09-12', NULL),
('PILLS789012', 'VWX76543210', '2024-12-25', '2025-12-24', NULL),
('RX123456789', 'EFG87654321', '2025-03-07', '2026-03-06', NULL),
('RXSTORE12345', 'ABC78901234', '2025-10-07', '2026-10-06', NULL),
('RXSTORE123456', 'ABC45678901', '2027-03-08', '2028-03-07', NULL),
('RXSTORE56789', 'STU32109876', '2024-11-30', '2025-11-29', NULL),
('RXSTORE567890', 'BCD67890123', '2026-07-06', '2027-07-05', NULL),
('RXSTORE789012', 'YZA23456789', '2027-11-30', '2028-11-29', NULL),
('VITAMINS12345', 'EFG78901234', '2026-08-25', '2027-08-24', NULL),
('VITAMINS34567', 'BCD34567890', '2027-12-28', '2028-12-27', NULL),
('VITAMINS789012', 'DEF56789012', '2027-04-04', '2028-04-02', NULL),
('VITAMINS8901', 'BCD54321098', '2025-02-09', '2026-02-08', NULL),
('VITAMINSHOP1', 'UVW56789012', '2025-08-24', '2026-08-23', NULL),
('WELLNESS2345', 'JKL87654321', '2024-08-22', '2025-08-21', NULL),
('WELLNESS6789', 'DEF89012345', '2025-11-30', '2026-11-29', NULL);

-- --------------------------------------------------------

--
-- Table structure for table `Cosmetic_Consultant`
--

CREATE TABLE `Cosmetic_Consultant` (
  `cosmetic_ssn` varchar(11) NOT NULL,
  `name` varchar(100) DEFAULT NULL,
  `gender` char(1) DEFAULT NULL,
  `specialty` varchar(100) DEFAULT NULL,
  `years_of_experience` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Cosmetic_Consultant`
--

INSERT INTO `Cosmetic_Consultant` (`cosmetic_ssn`, `name`, `gender`, `specialty`, `years_of_experience`) VALUES
('c1_555', 'Dr. Michael Johnson', 'F', 'Beauty Consultation', 5),
('c1_556', 'Dr. Benjamin Lee', 'F', 'Makeup Consultancy', 12),
('c1_557', 'Dr. Daniel Brown', 'F', 'Nail Care Guidance', 10),
('c1_558', 'Dr. Ethan Davis', 'F', 'Body Sculpting Consultation', 7),
('c1_559', 'Dr. Logan Clark', 'F', 'Hair Color Consultation', 6),
('c1_560', 'Dr. Jacob Garcia', 'F', 'Eyebrow Shaping Consultancy', 4),
('c1_561', 'Dr. Samuel Thompson', 'M', 'Men\'s Grooming Advice', 13),
('c1_562', 'Dr. Noah Rodriguez', 'F', 'Skin Analysis Services', 18),
('c1_563', 'Dr. Alexander White', 'M', 'Eyelash Extensions Advice', 14),
('c1_564', 'Dr. James Carter', 'F', 'Hair Extension Consultation', 17),
('c1_565', 'Dr. Ethan Lewis', 'F', 'Nutrition Counseling for Beauty', 16),
('c1_566', 'Dr. Liam Scott', 'M', 'Relaxation Therapy Sessions', 28),
('c1_567', 'Dr. Benjamin Baker', 'F', 'Massage Therapy Recommendations', 32),
('c1_568', 'Dr. Lucas Wright', 'M', 'Color Analysis for Makeup', 26),
('c1_569', 'Dr. William Hernandez', 'M', 'Microblading Services Consultancy', 24),
('c1_570', 'Dr. Madison Hill', 'M', 'Acne Treatment Consultation', 37),
('c1_571', 'Dr. Scarlett Evans', 'M', 'Nail Art Design Consultation', 33),
('c1_572', 'Dr. Stella Murphy', 'F', 'Beauty Sleep Consultation', 31),
('c1_573', 'Dr. Avery Cooper', 'F', 'Teen Skincare Guidance', 45),
('c1_574', 'Dr. Logan Brooks', 'F', 'Postpartum Beauty Tips', 42),
('c1_575', 'Dr. Aiden Parker', 'M', 'Makeup for Special Occasions', 39),
('c1_576', 'Dr. Sebastian Stewart', 'F', 'Hair Care Product Recommendations', 8),
('c1_577', 'Dr. Mia Russell', 'M', 'Beard Grooming Advice', 49),
('c1_578', 'Dr. Zoey Long', 'F', 'Eyelash and Brow Tinting Tips', 9),
('c1_579', 'Dr. Sophia Ward', 'F', 'Beauty Supplements Advice', 5),
('c2_666', 'Dr. Emily Williams', 'M', 'Skincare Advice', 8),
('c2_667', 'Dr. Sophia Taylor', 'M', 'Hair Styling Tips', 3),
('c2_668', 'Dr. Olivia Martinez', 'M', 'Aromatherapy Sessions', 15),
('c2_669', 'Dr. Ava Anderson', 'M', 'Wellness Counseling', 20),
('c2_670', 'Dr. Lily Moore', 'M', 'Facial Treatments Advice', 11),
('c2_671', 'Dr. Grace Wilson', 'F', 'Bridal Makeup Consultation', 9),
('c2_672', 'Dr. Isabella Harris', 'F', 'Anti-aging Solutions Consultation', 2),
('c2_673', 'Dr. Mia Jackson', 'F', 'Spa Treatment Consultancy', 25),
('c2_674', 'Dr. Harper Taylor', 'M', 'Makeup Application Classes', 22),
('c2_675', 'Dr. Emma Thomas', 'F', 'Waxing and Hair Removal Tips', 30),
('c2_676', 'Dr. Chloe Hall', 'F', 'Permanent Makeup Consultation', 23),
('c2_677', 'Dr. Amelia Green', 'M', 'Fitness Consultancy for Beauty', 19),
('c2_678', 'Dr. Charlotte Adams', 'F', 'Personalized Skincare Regimens', 21),
('c2_679', 'Dr. Evelyn King', 'F', 'Skin Tightening Consultation', 35),
('c2_680', 'Dr. Harper Reed', 'F', 'Holistic Beauty Advice', 29),
('c2_681', 'Dr. Mason Nelson', 'F', 'Scalp and Hair Health Consultancy', 27),
('c2_682', 'Dr. Elijah Allen', 'F', 'Body Contouring Advice', 40),
('c2_683', 'Dr. Jacob Rivera', 'M', 'Ayurvedic Beauty Consultancy', 38),
('c2_684', 'Dr. Lily Morris', 'M', 'Menopause Beauty Solutions', 36),
('c2_685', 'Dr. Violet Torres', 'F', 'Organic Beauty Consultation', 48),
('c2_686', 'Dr. Grace Collins', 'F', 'Fitness and Nutrition for Beauty', 46),
('c2_687', 'Dr. Addison Bailey', 'M', 'Makeup for Photography Consultation', 41),
('c2_688', 'Dr. Christopher Powell', 'F', 'Makeup for Film and TV Consultancy', 44),
('c2_689', 'Dr. Elijah Howard', 'M', 'Beauty Gadgets Consultation', 7),
('c2_690', 'Dr. Jackson Kelly', 'M', 'Hair Loss Solutions Consultation', 53);

-- --------------------------------------------------------

--
-- Table structure for table `Cosmetic_Product_Recommendation`
--

CREATE TABLE `Cosmetic_Product_Recommendation` (
  `Customer_ssn` varchar(11) NOT NULL,
  `Cosmetic_ssn` varchar(11) NOT NULL,
  `product_id` varchar(10) NOT NULL,
  `date` date DEFAULT NULL,
  `quantity` int(11) DEFAULT NULL,
  `recommendation` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Cosmetic_Product_Recommendation`
--

INSERT INTO `Cosmetic_Product_Recommendation` (`Customer_ssn`, `Cosmetic_ssn`, `product_id`, `date`, `quantity`, `recommendation`) VALUES
('107208618', 'c1_574', 'PRD039', '2027-03-31', 55, 104),
('293027303', 'c1_559', 'PRD009', '2024-09-12', 12, 124),
('221765913', 'c2_675', 'PRD020', '2025-08-15', 28, 126),
('841563709', 'c1_577', 'PRD045', '2027-09-14', 49, 147),
('656237820', 'c2_682', 'PRD034', '2026-10-29', 50, 189),
('103524599', 'c1_569', 'PRD029', '2026-05-28', 29, 204),
('847989489', 'c1_555', 'PRD001', '2024-03-01', 8, 213),
('858058860', 'c2_673', 'PRD016', '2025-04-08', 17, 231),
('715752453', 'c2_677', 'PRD024', '2025-12-26', 35, 247),
('145635245', 'c1_578', 'PRD047', '2027-11-08', 58, 249),
('185436850', 'c1_575', 'PRD041', '2027-05-25', 34, 293),
('701830274', 'c1_570', 'PRD031', '2026-07-22', 33, 318),
('773321809', 'c2_678', 'PRD026', '2026-02-19', 32, 319),
('743740583', 'c2_667', 'PRD004', '2024-01-20', 22, 325),
('236739784', 'c2_671', 'PRD012', '2024-12-30', 20, 354),
('461324683', 'c1_576', 'PRD043', '2027-07-20', 31, 365),
('405665656', 'c2_676', 'PRD022', '2025-10-30', 21, 398),
('265971709', 'c2_672', 'PRD014', '2025-02-14', 10, 435),
('862966222', 'c2_690', 'PRD050', '2028-02-14', 60, 435),
('112205133', 'c2_668', 'PRD006', '2024-06-03', 16, 451),
('180012276', 'c1_573', 'PRD037', '2027-01-06', 37, 451),
('750580920', 'c1_568', 'PRD027', '2026-03-04', 40, 476),
('675080805', 'c2_674', 'PRD018', '2025-06-21', 19, 478),
('823427114', 'c2_684', 'PRD038', '2027-02-17', 46, 527),
('811790823', 'c2_666', 'PRD002', '2024-02-15', 14, 543),
('746306110', 'c2_670', 'PRD010', '2024-10-25', 18, 569),
('914702626', 'c1_563', 'PRD017', '2025-05-19', 23, 569),
('450292233', 'c2_689', 'PRD048', '2027-12-21', 52, 571),
('143814089', 'c1_567', 'PRD025', '2026-01-08', 24, 582),
('890113046', 'c1_566', 'PRD023', '2025-11-13', 26, 615),
('882834297', 'c1_572', 'PRD035', '2026-11-11', 42, 630),
('326017990', 'c2_669', 'PRD008', '2024-08-29', 25, 632),
('627025907', 'c2_680', 'PRD030', '2026-06-10', 36, 647),
('912211978', 'c2_688', 'PRD046', '2027-10-26', 43, 683),
('622286126', 'c2_686', 'PRD042', '2027-06-08', 39, 718),
('934425637', 'c1_571', 'PRD033', '2026-09-17', 45, 742),
('758225875', 'c1_565', 'PRD021', '2025-09-27', 6, 754),
('358087207', 'c1_560', 'PRD011', '2024-11-07', 7, 786),
('607506150', 'c1_558', 'PRD007', '2024-07-18', 9, 789),
('118479648', 'c2_687', 'PRD044', '2027-08-02', 44, 820),
('244330761', 'c1_562', 'PRD015', '2025-03-26', 30, 870),
('499807881', 'c2_683', 'PRD036', '2026-12-24', 48, 872),
('572570798', 'c2_685', 'PRD040', '2027-04-13', 41, 876),
('736788461', 'c1_557', 'PRD005', '2024-05-10', 5, 876),
('123723403', 'c2_679', 'PRD028', '2026-04-16', 38, 895),
('502709076', 'c1_579', 'PRD049', '2028-01-03', 47, 903),
('577601827', 'c1_561', 'PRD013', '2025-01-02', 15, 921),
('335068216', 'c1_564', 'PRD019', '2025-07-04', 13, 943),
('719028295', 'c2_681', 'PRD032', '2026-08-05', 27, 965),
('910915353', 'c1_556', 'PRD003', '2024-04-05', 11, 987);

-- --------------------------------------------------------

--
-- Table structure for table `Customer`
--

CREATE TABLE `Customer` (
  `customer_ssn` varchar(11) NOT NULL,
  `name` char(20) DEFAULT NULL,
  `age` int(11) DEFAULT NULL,
  `address` varchar(20) DEFAULT NULL,
  `cosmetic_ssn` varchar(11) NOT NULL,
  `phone_number` varchar(20) DEFAULT NULL,
  `city` varchar(20) DEFAULT NULL,
  `last_name` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Customer`
--

INSERT INTO `Customer` (`customer_ssn`, `name`, `age`, `address`, `cosmetic_ssn`, `phone_number`, `city`, `last_name`) VALUES
('103524599', 'Christopher Parker', 39, '888 Pine Avenue', 'c1_569', '(818) 567-9012', 'Los Angeles', 'King'),
('107208618', 'Timothy Brooks', 28, '999 Walnut Road', 'c1_574', '(818) 678-2345', 'Los Angeles', 'Porter'),
('112205133', 'Jennifer Martinez', 28, '333 Cedar Road', 'c2_668', '(424) 901-2345', 'Los Angeles', 'Jones'),
('118479648', 'Heather Bell', 51, '555 Birch Avenue', 'c2_687', '(310) 234-9012', 'Pasadena', 'Jordan'),
('123723403', 'Lauren Collins', 24, '777 Cedar Street', 'c2_679', '(562) 456-6789', 'Long Beach', 'Young'),
('143814089', 'Benjamin Evans', 52, '444 Maple Street', 'c1_567', '(626) 123-5678', 'Long Beach', 'Walker'),
('145635245', 'Tyler Ramirez', 37, '888 Pine Avenue', 'c1_578', '(661) 567-9012', 'Long Beach', 'Douglas'),
('180012276', 'Brandon Richardson', 44, '777 Maple Street', 'c1_573', '(661) 456-6789', 'Santa Monica', 'Henderson'),
('185436850', 'Kyle Sanders', 58, '222 Pine Avenue', 'c1_575', '(323) 890-9012', 'Los Angeles', 'Foster'),
('221765913', 'Kimberly Scott', 26, '888 Birch Avenue', 'c2_675', '(310) 567-2345', 'Los Angeles', 'Robinson'),
('236739784', 'Ashley Rodriguez', 33, '999 Elm Road', 'c2_671', '(213) 678-1234', 'Pasadena', 'Thomas'),
('244330761', 'Robert Gonzalez', 40, '333 Walnut Road', 'c1_562', '(626) 901-2345', 'Los Angeles', 'Harris'),
('265971709', 'Elizabeth Lee', 20, '222 Birch Avenue', 'c2_672', '(310) 890-9012', 'Los Angeles', 'White'),
('293027303', 'James Garcia', 37, '666 Pine Road', 'c1_559', '(818) 345-0123', 'Santa Monica', 'Moore'),
('326017990', 'Amanda Anderson', 22, '555 Walnut Avenue', 'c2_669', '(562) 234-7890', 'Los Angeles', 'Wilson'),
('335068216', 'Joshua Wright', 47, '777 Maple Street', 'c1_564', '(818) 456-0123', 'Pasadena', 'Martinez'),
('358087207', 'Matthew Lopez', 27, '888 Oak Avenue', 'c1_560', '(323) 567-8901', 'Santa Monica', 'Anderson'),
('405665656', 'Nicole Adams', 60, '111 Cedar Street', 'c2_676', '(213) 789-2345', 'Los Angeles', 'Rodriguez'),
('450292233', 'Christina Ward', 54, '999 Oak Road', 'c2_689', '(562) 678-2345', 'Los Angeles', 'Fleming'),
('461324683', 'Kevin Price', 35, '444 Maple Street', 'c1_576', '(818) 123-5678', 'Pasadena', 'Collins'),
('499807881', 'Rachel Murphy', 57, '666 Oak Road', 'c2_683', '(424) 345-0123', 'Los Angeles', 'Simmons'),
('502709076', 'Bryan Powell', 26, '111 Maple Street', 'c1_579', '(818) 789-5678', 'Santa Monica', 'Fisher'),
('572570798', 'Christina Watson', 46, '111 Cedar Street', 'c2_685', '(310) 789-5678', 'Los Angeles', 'Palmer'),
('577601827', 'Daniel Martinez', 48, '111 Maple Street', 'c1_561', '(818) 789-5678', 'Los Angeles', 'Jackson'),
('607506150', 'Christopher Taylor', 50, '444 Birch Street', 'c1_558', '(661) 123-4567', 'Pasadena', 'Miller'),
('622286126', 'Kelly Alexander', 25, '333 Oak Road', 'c2_686', '(213) 901-2345', 'Long Beach', 'Burton'),
('627025907', 'Megan Morris', 56, '999 Oak Road', 'c2_680', '(310) 678-2345', 'Long Beach', 'Wright'),
('656237820', 'Brittany Bailey', 19, '444 Cedar Street', 'c2_682', '(310) 123-5678', 'Los Angeles', 'Foster'),
('675080805', 'Stephanie King', 32, '666 Oak Road', 'c2_674', '(562) 345-6789', 'Los Angeles', 'Garcia'),
('701830274', 'Jonathan Rivera', 21, '111 Maple Street', 'c1_570', '(323) 789-5678', 'Pasadena', 'Turner'),
('715752453', 'Samantha Stewart', 36, '333 Oak Road', 'c2_677', '(310) 901-2345', 'Los Angeles', 'Lee'),
('719028295', 'Amber Reed', 34, '222 Birch Avenue', 'c2_681', '(213) 890-9012', 'Los Angeles', 'Cooper'),
('736788461', 'Michael Wilson', 35, '222 Maple Avenue', 'c1_557', '(626) 890-5678', 'Los Angeles', 'Brown'),
('743740583', 'Sarah Davis', 18, '101 Elm Street', 'c2_667', '(213) 789-2345', 'Los Angeles', 'Davis'),
('746306110', 'Jessica Hernandez', 45, '777 Cedar Street', 'c2_670', '(310) 456-6789', 'Los Angeles', 'Taylor'),
('750580920', 'Andrew Turner', 43, '666 Walnut Road', 'c1_568', '(661) 345-0123', 'Los Angeles', 'Allen'),
('758225875', 'Ryan Green', 38, '999 Walnut Road', 'c1_565', '(323) 678-9012', 'Santa Monica', 'Clark'),
('773321809', 'Amanda Phillips', 31, '555 Birch Avenue', 'c2_678', '(424) 234-9012', 'Long Beach', 'Hall'),
('811790823', 'Emily Johnson', 30, '456 Oak Avenue', 'c2_666', '(310) 567-1234', 'Los Angeles', 'Johnson'),
('823427114', 'Michelle Wood', 53, '888 Birch Avenue', 'c2_684', '(562) 567-9012', 'Pasadena', 'Ward'),
('841563709', 'Gregory Howard', 30, '666 Walnut Road', 'c1_577', '(626) 345-0123', 'Los Angeles', 'Lawson'),
('847989489', 'John Smith', 25, '123 Main Street', 'c1_555', '(323) 456-7890', 'Los Angeles', 'Smith'),
('858058860', 'Melissa Perez', 29, '444 Cedar Street', 'c2_673', '(424) 123-5678', 'Santa Monica', 'Martin'),
('862966222', 'Emily Griffin', 33, '222 Birch Avenue', 'c2_690', '(310) 890-9012', 'Los Angeles', 'Weaver'),
('882834297', 'Justin Foster', 41, '555 Pine Avenue', 'c1_572', '(626) 234-9012', 'Los Angeles', 'Murphy'),
('890113046', 'Joseph Campbell', 23, '222 Pine Avenue', 'c1_566', '(818) 890-5678', 'Santa Monica', 'Lewis'),
('910915353', 'David Brown', 42, '789 Pine Road', 'c1_556', '(818) 678-9012', 'Los Angeles', 'Williams'),
('912211978', 'Tiffany Hayes', 22, '777 Cedar Street', 'c2_688', '(424) 456-6789', 'Los Angeles', 'Reed'),
('914702626', 'William Lewis', 55, '555 Pine Avenue', 'c1_563', '(661) 234-9012', 'Los Angeles', 'Thompson'),
('934425637', 'Nicholas Cook', 49, '333 Walnut Road', 'c1_571', '(818) 901-2345', 'Long Beach', 'Baker');

-- --------------------------------------------------------

--
-- Table structure for table `Manufacturing_Company`
--

CREATE TABLE `Manufacturing_Company` (
  `manufacturing_company_id` varchar(11) NOT NULL,
  `name` varchar(100) DEFAULT NULL,
  `phone_number` varchar(20) DEFAULT NULL,
  `supervisor` varchar(100) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Manufacturing_Company`
--

INSERT INTO `Manufacturing_Company` (`manufacturing_company_id`, `name`, `phone_number`, `supervisor`) VALUES
('ABC12345678', 'Starlight Cosmetics', '123-456-7890', 'John Smith'),
('ABC45678901', 'Opal Beauty', '654-321-0987', 'Amanda Cooper'),
('ABC78901234', 'Tranquil Spa', '987-654-3210', 'William Scott'),
('BCD34567890', 'Zenith Beauty', '765-432-1098', 'Benjamin Ward'),
('BCD54321098', 'Crystal Clear Beauty', '109-876-5432', 'James Rodriguez'),
('BCD67890123', 'Zen Beauty Co.', '432-109-8765', 'Rebecca Baker'),
('DEF45678901', 'Radiant Skin Care', '345-678-9012', 'Michael Brown'),
('DEF56789012', 'Tranquility Spa', '543-210-9876', 'Christopher Bailey'),
('DEF89012345', 'Elegance Beauty', '890-123-4567', 'Elizabeth White'),
('EFG45678901', 'Lush Cosmetics', '654-321-0987', 'Kimberly Ramirez'),
('EFG78901234', 'Harmony Beauty', '321-098-7654', 'Ryan Martinez'),
('EFG87654321', 'Zenith Cosmetics', '210-987-6543', 'Ashley Lee'),
('GHI23456789', 'Pure Essence', '456-789-0123', 'Emily Davis'),
('GHI67890123', 'Ethereal Cosmetics', '432-109-8765', 'Emily Carter'),
('GHI90123456', 'Aurora Cosmetics', '901-234-5678', 'Joseph Martinez'),
('HIJ56789012', 'Harmony Skincare', '543-210-9876', 'Jonathan Powell'),
('HIJ89012345', 'Luminous Cosmetics', '210-987-6543', 'Megan Parker'),
('HIJ98765432', 'Divine Glow', '321-098-7654', 'Robert Perez'),
('JKL01234567', 'Enchanted Beauty', '012-345-6789', 'Kimberly Moore'),
('JKL78901234', 'Radiant Beauty', '321-098-7654', 'Jason Torres'),
('JKL87654321', 'Luxe Cosmetics', '567-890-1234', 'Daniel Martinez'),
('LMN23456789', 'Serene Skincare', '432-109-8765', 'Melissa Harris'),
('LMN67890123', 'Aurora Beauty', '432-109-8765', 'Tiffany Ross'),
('LMN90123456', 'Luxe Skincare', '109-876-5432', 'Brian Adams'),
('MNO12345678', 'Blossom Beauty', '987-654-3210', 'Daniel Lopez'),
('MNO54321098', 'Harmony Naturals', '678-901-2345', 'Jessica Anderson'),
('MNO89012345', 'Renew Cosmetics', '210-987-6543', 'Maria Reed'),
('OPQ01234567', 'Divine Beauty', '098-765-4321', 'Lauren Rivera'),
('OPQ34567890', 'Renew Beauty', '543-210-9876', 'Matthew Clark'),
('OPQ78901234', 'Blissful Spa', '321-098-7654', 'Brandon Butler'),
('PQR10987654', 'Glow Beauty Co.', '789-012-3456', 'Christopher Taylor'),
('PQR23456789', 'Radiance Skincare', '876-543-2109', 'Michelle Green'),
('PQR90123456', 'Blossom Spa', '109-876-5432', 'Justin Russell'),
('RST12345678', 'Vitality Spa', '987-654-3210', 'Kevin Evans'),
('RST45678901', 'Velvet Skin', '654-321-0987', 'Samantha King'),
('RST89012345', 'Pure Radiance', '210-987-6543', 'Christina James'),
('STU01234567', 'Crystal Skincare', '098-765-4321', 'Laura Nelson'),
('STU32109876', 'Serenity Spa', '890-123-4567', 'Jennifer Wilson'),
('STU34567890', 'Pure Harmony', '765-432-1098', 'Charles Young'),
('UVW23456789', 'Bliss Beauty', '876-543-2109', 'Rachel Mitchell'),
('UVW56789012', 'Ethereal Beauty', '765-432-1098', 'Joshua Wright'),
('VWX12345678', 'Enchanted Cosmetics', '987-654-3210', 'Nicholas Hughes'),
('VWX45678901', 'Crystal Beauty', '654-321-0987', 'Stephanie Hall'),
('VWX76543210', 'Vitality Beauty', '901-234-5678', 'David Garcia'),
('XYZ34567890', 'Velvet Cosmetics', '765-432-1098', 'Anthony Phillips'),
('XYZ67890123', 'Opulence Cosmetics', '876-543-2109', 'Nicole Turner'),
('XYZ98765432', 'Belle Beauty', '234-567-8901', 'Sarah Johnson'),
('YZA23456789', 'Serene Beauty Co.', '876-543-2109', 'Erica Coleman'),
('YZA56789012', 'Serenity Glow', '543-210-9876', 'Andrew Gonzalez'),
('YZA89012345', 'Blissful Cosmetics', '098-765-4321', 'Amanda Thomas');

-- --------------------------------------------------------

--
-- Table structure for table `Pharmacy`
--

CREATE TABLE `Pharmacy` (
  `pharmacy_id` varchar(20) NOT NULL,
  `name` varchar(100) DEFAULT NULL,
  `address` varchar(100) DEFAULT NULL,
  `phone_number` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Pharmacy`
--

INSERT INTO `Pharmacy` (`pharmacy_id`, `name`, `address`, `phone_number`) VALUES
('CAREPHARM12345', 'PHARMA Market', '222 Willow Road, Villagetown, State, Zip Code', '109-876-5432'),
('CAREPHARM234', 'PHARMA Choice', '111 Pine Lane, Villageton, State, Zip Code', '321-098-7654'),
('CAREPHARM3456', 'PHARMA Point', '454 Elm Avenue, Hamletville, State, Zip Code', '765-432-1098'),
('CAREPHARM45678', 'PHARMA Junction', '323 Main Street, Townsville, State, Zip Code', '987-654-3210'),
('CAREPHARM78901', 'PHARMA Ground', '123 Spruce Lane, Townsville, State, Zip Code', '321-098-7654'),
('DRUGS890123', 'PHARMA Zone', '333 Maple Street, Hamletton, State, Zip Code', '543-210-9876'),
('DRUGSTORE123456', 'PHARMA Land', '999 Birch Avenue, Citytown, State, Zip Code', '432-109-8765'),
('DRUGSTORE567890', 'PHARMA Depot', '111 Spruce Lane, Hamletton, State, Zip Code', '210-987-6543'),
('DRUGSTORE678', 'PHARMA Care', '456 Elm Avenue, Townsville, State, Zip Code', '234-567-8901'),
('DRUGSTORE89012', 'PHARMA Care', '343 Oak Road, Townsville, State, Zip Code', '876-543-2109'),
('DRUGSTORE90123', 'PHARMA Source', '212 Willow Road, Citytown, State, Zip Code', '098-765-4321'),
('HEALTHCARE1234', 'PHARMA Lane', '434 Elm Avenue, Villageton, State, Zip Code', '876-543-2109'),
('HEALTHCARE23456', 'PHARMA Coast', '234 Maple Street, Hamletton, State, Zip Code', '210-987-6543'),
('HEALTHCARE567', 'PHARMA Village', '222 Cedar Avenue, Citytown, State, Zip Code', '432-109-8765'),
('HEALTHCARE6789', 'PHARMA Center', '333 Main Street, Cityville, State, Zip Code', '098-765-4321'),
('HEALTHCARE7890', 'PHARMA Store', '565 Birch Avenue, Villageton, State, Zip Code', '654-321-0987'),
('HEALTHCARE901', 'PHARMA World', '789 Oak Road, Villagetown, State, Zip Code', '345-678-9012'),
('HEALTHY23456', 'PHARMA Way', '999 Main Street, Hamletton, State, Zip Code', '901-234-5678'),
('HEALTHY34567', 'PHARMA Depot', '707 Willow Road, Villagetown, State, Zip Code', '098-765-4321'),
('HEALTHY345678', 'PHARMA Bay', '878 Cedar Avenue, Citytown, State, Zip Code', '432-109-8765'),
('HEALTHY678901', 'PHARMA Outlet', '909 Cedar Avenue, Hamletton, State, Zip Code', '210-987-6543'),
('HEALTHY890123', 'PHARMA Reach', '777 Main Street, Hamletville, State, Zip Code', '654-321-0987'),
('MEDICAL123456', 'PHARMA Shop', '676 Spruce Lane, Citytown, State, Zip Code', '543-210-9876'),
('MEDICAL234567', 'PHARMA Spot', '444 Elm Avenue, Townsville, State, Zip Code', '987-654-3210'),
('MEDICAL45678', 'PHARMA Health', '101 Pine Lane, Hamletville, State, Zip Code', '456-789-0123'),
('MEDICAL456789', 'PHARMA City', '444 Spruce Lane, Villagetown, State, Zip Code', '654-321-0987'),
('MEDICAL567890', 'PHARMA Plaza', '545 Birch Avenue, Cityville, State, Zip Code', '765-432-1098'),
('MEDICINE1234', 'PHARMA Wellness', '404 Birch Road, Citytown, State, Zip Code', '789-012-3456'),
('MEDICINE78901', 'PHARMA Market', '121 Maple Street, Villagetown, State, Zip Code', '012-345-6789'),
('PHARMA12345', 'PHARMA Plus', '123 Main Street, Cityville, State, Zip Code', '123-456-7890'),
('PHARMA234567', 'PHARMA Line', '232 Cedar Avenue, Citytown, State, Zip Code', '987-654-3210'),
('PHARMA2345678', 'PHARMA Outlet', '101 Oakwood Avenue, Villagetown, State, Zip Code', '109-876-5432'),
('PHARMA456789', 'PHARMA Haven', '888 Elm Street, Villagetown, State, Zip Code', '543-210-9876'),
('PHARMA901234', 'PHARMA Network', '989 Oak Road, Townsville, State, Zip Code', '321-098-7654'),
('PHARMACY7890', 'PHARMA Express', '303 Cedar Avenue, Townville, State, Zip Code', '678-901-2345'),
('PILLS456789', 'PHARMA Drive', '666 Willow Road, Townsville, State, Zip Code', '876-543-2109'),
('PILLS789012', 'PHARMA Mart', '606 Oakwood Avenue, Cityville, State, Zip Code', '901-234-5678'),
('RX123456789', 'PHARMA Center', '909 Birch Avenue, Townsville, State, Zip Code', '210-987-6543'),
('RXSTORE12345', 'PHARMA Stop', '777 Elm Street, Villageton, State, Zip Code', '987-654-3210'),
('RXSTORE123456', 'PHARMA Express', '656 Pine Lane, Hamletville, State, Zip Code', '654-321-0987'),
('RXSTORE56789', 'PHARMA Aid', '505 Spruce Lane, Hamletton, State, Zip Code', '890-123-4567'),
('RXSTORE567890', 'PHARMA Place', '787 Pine Lane, Townsville, State, Zip Code', '432-109-8765'),
('RXSTORE789012', 'PHARMA Avenue', '555 Oakwood Avenue, Villageton, State, Zip Code', '876-543-2109'),
('VITAMINS12345', 'PHARMA Hub', '898 Maple Street, Cityville, State, Zip Code', '321-098-7654'),
('VITAMINS34567', 'PHARMA Circle', '666 Cedar Avenue, Citytown, State, Zip Code', '765-432-1098'),
('VITAMINS789012', 'PHARMA Connection', '767 Maple Street, Villagetown, State, Zip Code', '543-210-9876'),
('VITAMINS8901', 'PHARMA Spot', '808 Elm Street, Hamletville, State, Zip Code', '109-876-5432'),
('VITAMINSHOP1', 'PHARMA Link', '555 Oakwood Avenue, Cityville, State, Zip Code', '765-432-1098'),
('WELLNESS2345', 'PHARMA Life', '202 Maple Street, Villageton, State, Zip Code', '567-890-1234'),
('WELLNESS6789', 'PHARMA Corner', '888 Birch Avenue, Citytown, State, Zip Code', '890-123-4567');

-- --------------------------------------------------------

--
-- Table structure for table `PharmacyEmployee`
--

CREATE TABLE `PharmacyEmployee` (
  `employee_id` varchar(100) NOT NULL,
  `name` varchar(100) DEFAULT NULL,
  `position` varchar(100) DEFAULT NULL,
  `pharmacy_id` varchar(20) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `PharmacyEmployee`
--

INSERT INTO `PharmacyEmployee` (`employee_id`, `name`, `position`, `pharmacy_id`) VALUES
('e-451', 'Harper Reed', 'Pharmacy Auditor', 'CAREPHARM12345'),
('e-143', 'Amelia Lee', 'Lead Pharmacy Technician', 'CAREPHARM234'),
('e-275', 'Scarlett Thomas', 'Home Infusion Pharmacist', 'CAREPHARM3456'),
('e-363', 'Grace Edwards', 'Psychiatric Pharmacist', 'CAREPHARM45678'),
('e-539', 'Aiden Hayes', 'Pharmacy Data Analyst', 'CAREPHARM78901'),
('e-165', 'Evelyn Davis', 'Hospital Pharmacist', 'DRUGS890123'),
('e-528', 'Emma Griffin', 'Pharmacy IT Specialist', 'DRUGSTORE123456'),
('e-440', 'Evelyn Hayes', 'Pharmacy Auditor', 'DRUGSTORE567890'),
('e-22', 'Olivia Smith', 'Pharmacist', 'DRUGSTORE678'),
('e-264', 'Logan Garcia', 'Geriatric Pharmacist', 'DRUGSTORE89012'),
('e-352', 'Elijah Wright', 'Transplant Pharmacist', 'DRUGSTORE90123'),
('e-374', 'Harper Hill', 'Infectious Disease Pharmacist', 'HEALTHCARE1234'),
('e-540', 'lia Hayes', 'Pharmacy Data Analyst', 'HEALTHCARE23456'),
('e-154', 'Harper Perez', 'Retail Pharmacist', 'HEALTHCARE567'),
('e-462', 'Grace Russell', 'Pharmacy Educator', 'HEALTHCARE6789'),
('e-286', 'Chloe Hall', 'Institutional Pharmacist', 'HEALTHCARE7890'),
('e-33', 'Ethan Williams', 'Pharmacy Assistant', 'HEALTHCARE901'),
('e-231', 'Sebastian Harris', 'Long-Term Care Pharmacist', 'HEALTHY23456'),
('e-110', 'Benjamin Anderson', 'Clinical Pharmacist', 'HEALTHY34567'),
('e-418', 'Emma Rivera', 'Pharmacy Auditor', 'HEALTHY345678'),
('e-330', 'Mason Parker', 'Clinical Research Pharmacist', 'HEALTHY678901'),
('e-506', 'Zoey Campbell', 'Medication Safety Officer', 'HEALTHY890123'),
('e-297', 'Jackson Lewis', 'Industrial Pharmacist', 'MEDICAL123456'),
('e-473', 'Christopher Baker', 'Pharmacy Consultant', 'MEDICAL234567'),
('e-44', 'Ava Brown', 'Pharmacy Manager', 'MEDICAL45678'),
('e-176', 'Samuel Rodriguez', 'Community Pharmacist', 'MEDICAL456789'),
('e-385', 'William Rogers', 'Retail Pharmacy Manager', 'MEDICAL567890'),
('e-77', 'Isabella Taylor', 'Pharmacy Technician Trainee', 'MEDICINE1234'),
('e-242', 'Aiden Taylor', 'Ambulatory Care Pharmacist', 'MEDICINE78901'),
('e-11', 'Liam Johnson', 'Pharmacy Technician', 'PHARMA12345'),
('e-253', 'Grace Moore', 'Pediatric Pharmacist', 'PHARMA234567'),
('e-341', 'Zoey Phillips', 'Oncology Pharmacist', 'PHARMA2345678'),
('e-517', 'Ethan Parker', 'Medication Safety Officer', 'PHARMA456789'),
('e-429', 'Lucas Nelson', 'Pharmacy Auditor', 'PHARMA901234'),
('e-66', 'Noah Miller', 'Pharmacy Intern', 'PHARMACY7890'),
('e-198', 'Daniel Clark', 'Inpatient Pharmacist', 'PILLS456789'),
('e-99', 'Sophia Martin', 'Pharmacy Director', 'PILLS789012'),
('e-132', 'Alexander Harris', 'Certified Pharmacy Technician', 'RX123456789'),
('e-209', 'Harper Jackson', 'Outpatient Pharmacist', 'RXSTORE12345'),
('e-396', 'Addison Murphy', 'Retail Pharmacy Manager', 'RXSTORE123456'),
('e-88', 'James Wilson', 'Compounding Pharmacist', 'RXSTORE56789'),
('e-308', 'Lily Turner', 'Regulatory Affairs Pharmacist', 'RXSTORE567890'),
('e-484', 'Elijah Young', 'Pharmacy Liaison', 'RXSTORE789012'),
('e-319', 'Christopher Cooper', 'Drug Information Pharmacist', 'VITAMINS12345'),
('e-495', 'Mason Mitchell', 'Medication Safety Officer', 'VITAMINS34567'),
('e-407', 'Elijah Carter', 'Clinical Pharmacy Manager', 'VITAMINS789012'),
('e-121', 'Charlotte Thompson', 'Staff Pharmacist', 'VITAMINS8901'),
('e-187', 'Lily Martinez', 'Pharmacy Specialist', 'VITAMINSHOP1'),
('e-55', 'Mia Jones', 'Pharmacy Clerk', 'WELLNESS2345'),
('e-220', 'Madison White', 'Nuclear Pharmacist', 'WELLNESS6789');

-- --------------------------------------------------------

--
-- Table structure for table `Product`
--

CREATE TABLE `Product` (
  `product_id` varchar(10) NOT NULL,
  `description` varchar(1000) DEFAULT NULL,
  `brand` varchar(20) DEFAULT NULL,
  `manufacturing_company_id` varchar(11) NOT NULL,
  `prod_name` varchar(300) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Product`
--

INSERT INTO `Product` (`product_id`, `description`, `brand`, `manufacturing_company_id`, `prod_name`) VALUES
('PRD001', 'A luxurious moisturizing cream enriched with vitamins and antioxidants to hydrate and nourish the skin.', 'Aurora Beauty', 'ABC12345678', 'Moisturizing Cream'),
('PRD002', 'An advanced anti-aging serum formulated with peptides and hyaluronic acid to reduce fine lines and wrinkles.', 'Luxe Cosmetics', 'XYZ98765432', 'Anti-Aging Serum'),
('PRD003', 'A gentle exfoliating scrub infused with natural fruit extracts to brighten and smooth the complexion.', 'Radiant Skincare', 'DEF45678901', 'Exfoliating Scrub'),
('PRD004', 'A deeply hydrating mask containing aloe vera and shea butter to soothe and replenish dry skin.', 'Harmony Naturals', 'GHI23456789', 'Hydrating Mask'),
('PRD005', 'A refreshing brightening toner with vitamin C and green tea extract to even out skin tone and texture.', 'Divine Glow', 'JKL87654321', 'Brightening Toner'),
('PRD006', 'A lightweight sunscreen lotion with SPF 50 to provide broad-spectrum protection against harmful UV rays.', 'Serenity Spa', 'MNO54321098', 'Sunscreen Lotion'),
('PRD007', 'An effective cleansing oil that effortlessly removes makeup and impurities without stripping the skin\'s natural oils.', 'Vitality Beauty', 'PQR10987654', 'Cleansing Oil'),
('PRD008', 'A nourishing night cream enriched with retinol and collagen to promote overnight skin renewal and repair.', 'Pure Essence', 'STU32109876', 'Night Cream'),
('PRD009', 'A revitalizing eye serum infused with caffeine and peptides to reduce puffiness and dark circles.', 'Blissful Cosmetics', 'VWX76543210', 'Eye Serum'),
('PRD010', 'A targeted acne treatment gel containing salicylic acid and tea tree oil to unclog pores and prevent breakouts.', 'Crystal Clear', 'YZA89012345', 'Acne Treatment'),
('PRD011', 'A hydrating lip balm enriched with shea butter and coconut oil to soften and condition dry lips.', 'Zenith Beauty', 'BCD54321098', 'Lip Balm'),
('PRD012', 'An effective makeup remover micellar water that gently lifts away dirt, oil, and makeup residue.', 'Blossom Beauty', 'EFG87654321', 'Makeup Remover'),
('PRD013', 'A refreshing facial mist infused with rose water and botanical extracts to hydrate and refresh the skin throughout the day.', 'Ethereal Cosmetics', 'HIJ98765432', 'Facial Mist'),
('PRD014', 'A lightweight body lotion with cocoa butter and almond oil to moisturize and soften the skin.', 'Opulence Cosmetics', 'LMN23456789', 'Body Lotion'),
('PRD015', 'An ultra-rich hand cream infused with shea butter and glycerin to nourish and protect dry hands.', 'Tranquil Spa', 'OPQ34567890', 'Hand Cream'),
('PRD016', 'A nourishing hair conditioner enriched with argan oil and keratin to smooth and detangle hair strands.', 'Serene Skincare', 'RST45678901', 'Hair Conditioner'),
('PRD017', 'A volumizing shampoo with biotin and collagen to strengthen and thicken fine, limp hair.', 'Renew Beauty', 'UVW56789012', 'Shampoo'),
('PRD018', 'A hydrating body wash infused with coconut milk and honey to cleanse and moisturize the skin.', 'Velvet Cosmetics', 'XYZ67890123', 'Body Wash'),
('PRD019', 'A soothing foot cream containing peppermint and eucalyptus oil to cool and relieve tired, achy feet.', 'Luminous Cosmetics', 'ABC78901234', 'Foot Cream'),
('PRD020', 'A long-lasting deodorant stick with a fresh citrus scent to keep you feeling confident and odor-free.', 'Aurora Cosmetics', 'DEF89012345', 'Deodorant'),
('PRD021', 'A floral perfume with notes of jasmine and rose for a feminine and romantic fragrance.', 'Enchanted Beauty', 'GHI90123456', 'Perfume'),
('PRD022', 'A lightweight face oil infused with squalane and vitamin E to nourish and balance the skin\'s moisture levels.', 'Radiance Skincare', 'JKL01234567', 'Face Oil'),
('PRD023', 'A revitalizing body scrub with sea salt and essential oils to exfoliate and smooth rough, dry skin.', 'Crystal Beauty', 'MNO12345678', 'Body Scrub'),
('PRD024', 'A high-shine nail polish in a vibrant red hue for a bold and glamorous manicure.', 'Serenity Glow', 'PQR23456789', 'Nail Polish'),
('PRD025', 'A moisturizing lip gloss with a non-sticky formula and a hint of shimmer for a plump, glossy pout.', 'Zen Beauty Co.', 'STU34567890', 'Lip Gloss'),
('PRD026', 'A hydrating face primer infused with hyaluronic acid and silicone to smooth and prep the skin for makeup application.', 'Harmony Beauty', 'VWX45678901', 'Face Primer'),
('PRD027', 'A long-lasting makeup setting spray that locks makeup in place for up to 16 hours without smudging or fading.', 'Divine Beauty', 'YZA56789012', 'Setting Spray'),
('PRD028', 'A waterproof eyeliner pencil with a creamy texture and intense color payoff for precise and defined eye looks.', 'Vitality Spa', 'BCD67890123', 'Eyeliner'),
('PRD029', 'A volumizing mascara with a curved wand and carbon black formula for dramatic lash volume and length.', 'Bliss Beauty', 'EFG78901234', 'Mascara'),
('PRD030', 'A versatile eyeshadow palette with a range of matte and shimmer shades for creating endless eye looks.', 'Velvet Cosmetics', 'HIJ89012345', 'Eyeshadow Palette'),
('PRD031', 'A lightweight liquid foundation with buildable coverage and a natural satin finish for a flawless complexion.', 'Opal Beauty', 'LMN90123456', 'Foundation'),
('PRD032', 'A creamy concealer with a doe-foot applicator for seamless coverage of dark circles and blemishes.', 'Tranquility Spa', 'OPQ01234567', 'Concealer'),
('PRD033', 'A silky blush powder in a peachy pink shade for a natural flush of color on the cheeks.', 'Ethereal Cosmetics', 'RST12345678', 'Blush'),
('PRD034', 'A matte bronzer powder in a warm, sun-kissed shade for contouring and adding warmth to the complexion.', 'Radiant Beauty', 'UVW23456789', 'Bronzer'),
('PRD035', 'A luminous highlighter powder with a champagne gold hue for a radiant glow on the high points of the face.', 'Renew Cosmetics', 'XYZ34567890', 'Highlighter'),
('PRD036', 'A creamy lipstick with a satin finish and rich color payoff for smooth and comfortable wear.', 'Blossom Spa', 'ABC45678901', 'Lipstick'),
('PRD037', 'A long-wearing lip liner pencil with a creamy texture and precise tip for defining and shaping the lips.', 'Crystal Skincare', 'DEF56789012', 'Lip Liner'),
('PRD038', 'A translucent loose powder with micro-fine particles to set makeup and control shine for a matte finish.', 'Enchanted Cosmetics', 'GHI67890123', 'Makeup Setting Powder'),
('PRD039', 'A refreshing makeup setting spray infused with cucumber and green tea to hydrate and revitalize the skin.', 'Serene Beauty Co.', 'JKL78901234', 'Makeup Setting Spray'),
('PRD040', 'A professional makeup brush set with synthetic bristles and ergonomic handles for flawless makeup application.', 'Zenith Beauty', 'MNO89012345', 'Makeup Brush Set'),
('PRD041', 'A soft and bouncy makeup sponge for seamless blending of liquid and cream products.', 'Lush Cosmetics', 'PQR90123456', 'Makeup Sponge'),
('PRD042', 'A dual-ended eyebrow pencil with a pencil tip and spoolie brush for shaping and defining brows.', 'Harmony Skincare', 'STU01234567', 'Eyebrow Pencil'),
('PRD043', 'A tinted eyebrow gel with fibers to fill in sparse areas and hold brows in place all day.', 'Aurora Beauty', 'VWX12345678', 'Eyebrow Gel'),
('PRD044', 'A creamy eyebrow pomade with a waterproof formula for sculpting and filling in brows with precision.', 'Blissful Spa', 'YZA23456789', 'Eyebrow Pomade'),
('PRD045', 'A finely milled eyebrow powder in a natural taupe shade for softly defining and shading brows.', 'Pure Radiance', 'BCD34567890', 'Eyebrow Powder'),
('PRD046', 'A clear eyebrow wax with a long-lasting formula for setting and grooming unruly brows.', 'Crystal Beauty', 'EFG45678901', 'Eyebrow Wax'),
('PRD047', 'A set of reusable eyebrow stencils in various shapes for achieving perfectly arched brows.', 'Serenity Glow', 'HIJ56789012', 'Eyebrow Stencil'),
('PRD048', 'A tinted eyebrow tint with a gel formula for tinting and defining brows with natural-looking color.', 'Zen Beauty Co.', 'LMN67890123', 'Eyebrow Tint'),
('PRD049', 'A volumizing eyebrow mascara with a small brush for grooming and setting brows in place.', 'Harmony Beauty', 'OPQ78901234', 'Eyebrow Mascara'),
('PRD050', 'A precision eyebrow razor with a sharp blade and safety guard for shaping and sculpting brows with ease.', 'Luxe Skincare', 'RST89012345', 'Eyebrow Razor');

-- --------------------------------------------------------

--
-- Table structure for table `Sell`
--

CREATE TABLE `Sell` (
  `price` int(11) DEFAULT NULL,
  `pharmacy_id` varchar(20) NOT NULL,
  `product_id` varchar(10) NOT NULL,
  `category` varchar(50) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data for table `Sell`
--

INSERT INTO `Sell` (`price`, `pharmacy_id`, `product_id`, `category`) VALUES
(150, 'CAREPHARM12345', 'PRD041', 'Makeup'),
(132, 'CAREPHARM234', 'PRD013', 'Skincare'),
(128, 'CAREPHARM3456', 'PRD025', 'Makeup'),
(222, 'CAREPHARM45678', 'PRD033', 'Makeup'),
(254, 'CAREPHARM78901', 'PRD049', 'Makeup'),
(174, 'DRUGS890123', 'PRD015', 'Skincare'),
(73, 'DRUGSTORE123456', 'PRD048', 'Makeup'),
(77, 'DRUGSTORE567890', 'PRD040', 'Makeup'),
(145, 'DRUGSTORE678', 'PRD002', 'Skincare'),
(201, 'DRUGSTORE89012', 'PRD024', 'Nailcare'),
(101, 'DRUGSTORE90123', 'PRD032', 'Makeup'),
(136, 'HEALTHCARE1234', 'PRD034', 'Makeup'),
(260, 'HEALTHCARE23456', 'PRD050', 'Makeup'),
(218, 'HEALTHCARE567', 'PRD014', 'Skincare'),
(203, 'HEALTHCARE6789', 'PRD042', 'Makeup'),
(84, 'HEALTHCARE7890', 'PRD026', 'Makeup'),
(89, 'HEALTHCARE901', 'PRD003', 'Skincare'),
(294, 'HEALTHY23456', 'PRD021', 'Fragrance'),
(63, 'HEALTHY34567', 'PRD010', 'Skincare'),
(109, 'HEALTHY345678', 'PRD038', 'Makeup'),
(48, 'HEALTHY678901', 'PRD030', 'Makeup'),
(127, 'HEALTHY890123', 'PRD046', 'Makeup'),
(162, 'MEDICAL123456', 'PRD027', 'Makeup'),
(133, 'MEDICAL234567', 'PRD043', 'Makeup'),
(203, 'MEDICAL45678', 'PRD004', 'Skincare'),
(95, 'MEDICAL456789', 'PRD016', 'Haircare'),
(61, 'MEDICAL567890', 'PRD035', 'Makeup'),
(176, 'MEDICINE1234', 'PRD007', 'Skincare'),
(38, 'MEDICINE78901', 'PRD022', 'Skincare'),
(27, 'PHARMA12345', 'PRD001', 'Skincare'),
(269, 'PHARMA234567', 'PRD023', 'Body Care'),
(239, 'PHARMA2345678', 'PRD031', 'Makeup'),
(295, 'PHARMA456789', 'PRD047', 'Makeup'),
(254, 'PHARMA901234', 'PRD039', 'Makeup'),
(284, 'PHARMACY7890', 'PRD006', 'Skincare'),
(122, 'PILLS456789', 'PRD018', 'Body Care'),
(251, 'PILLS789012', 'PRD009', 'Skincare'),
(76, 'RX123456789', 'PRD012', 'Skincare'),
(246, 'RXSTORE12345', 'PRD019', 'Body Care'),
(292, 'RXSTORE123456', 'PRD036', 'Makeup'),
(112, 'RXSTORE56789', 'PRD008', 'Skincare'),
(115, 'RXSTORE567890', 'PRD028', 'Makeup'),
(66, 'RXSTORE789012', 'PRD044', 'Makeup'),
(278, 'VITAMINS12345', 'PRD029', 'Makeup'),
(287, 'VITAMINS34567', 'PRD045', 'Makeup'),
(181, 'VITAMINS789012', 'PRD037', 'Makeup'),
(199, 'VITAMINS8901', 'PRD011', 'Skincare'),
(287, 'VITAMINSHOP1', 'PRD017', 'Haircare'),
(57, 'WELLNESS2345', 'PRD005', 'Skincare'),
(71, 'WELLNESS6789', 'PRD020', 'Body Care');

--
-- Indexes for dumped tables
--

--
-- Indexes for table `Allergic`
--
ALTER TABLE `Allergic`
  ADD PRIMARY KEY (`customer_ssn`);

--
-- Indexes for table `Contract`
--
ALTER TABLE `Contract`
  ADD PRIMARY KEY (`pharmacy_id`,`manufacturing_company_id`),
  ADD KEY `manufacturing_company_id` (`manufacturing_company_id`);

--
-- Indexes for table `Cosmetic_Consultant`
--
ALTER TABLE `Cosmetic_Consultant`
  ADD PRIMARY KEY (`cosmetic_ssn`);

--
-- Indexes for table `Cosmetic_Product_Recommendation`
--
ALTER TABLE `Cosmetic_Product_Recommendation`
  ADD PRIMARY KEY (`recommendation`,`Customer_ssn`,`Cosmetic_ssn`,`product_id`),
  ADD KEY `Customer_ssn` (`Customer_ssn`),
  ADD KEY `Cosmetic_ssn` (`Cosmetic_ssn`),
  ADD KEY `product_id` (`product_id`);

--
-- Indexes for table `Customer`
--
ALTER TABLE `Customer`
  ADD PRIMARY KEY (`customer_ssn`),
  ADD KEY `cosmetic_ssn` (`cosmetic_ssn`);

--
-- Indexes for table `Manufacturing_Company`
--
ALTER TABLE `Manufacturing_Company`
  ADD PRIMARY KEY (`manufacturing_company_id`);

--
-- Indexes for table `Pharmacy`
--
ALTER TABLE `Pharmacy`
  ADD PRIMARY KEY (`pharmacy_id`);

--
-- Indexes for table `PharmacyEmployee`
--
ALTER TABLE `PharmacyEmployee`
  ADD PRIMARY KEY (`pharmacy_id`,`employee_id`);

--
-- Indexes for table `Product`
--
ALTER TABLE `Product`
  ADD PRIMARY KEY (`product_id`),
  ADD KEY `manufacturing_company_id` (`manufacturing_company_id`);

--
-- Indexes for table `Sell`
--
ALTER TABLE `Sell`
  ADD PRIMARY KEY (`pharmacy_id`,`product_id`),
  ADD KEY `product_id` (`product_id`);

--
-- Constraints for dumped tables
--

--
-- Constraints for table `Allergic`
--
ALTER TABLE `Allergic`
  ADD CONSTRAINT `Allergic_ibfk_1` FOREIGN KEY (`customer_ssn`) REFERENCES `Customer` (`customer_ssn`) ON DELETE CASCADE ON UPDATE CASCADE;

--
-- Constraints for table `Contract`
--
ALTER TABLE `Contract`
  ADD CONSTRAINT `Contract_ibfk_1` FOREIGN KEY (`pharmacy_id`) REFERENCES `Pharmacy` (`pharmacy_id`),
  ADD CONSTRAINT `Contract_ibfk_2` FOREIGN KEY (`manufacturing_company_id`) REFERENCES `Manufacturing_Company` (`manufacturing_company_id`);

--
-- Constraints for table `Cosmetic_Product_Recommendation`
--
ALTER TABLE `Cosmetic_Product_Recommendation`
  ADD CONSTRAINT `Cosmetic_Product_Recommendation_ibfk_1` FOREIGN KEY (`Customer_ssn`) REFERENCES `Customer` (`customer_ssn`),
  ADD CONSTRAINT `Cosmetic_Product_Recommendation_ibfk_2` FOREIGN KEY (`Cosmetic_ssn`) REFERENCES `Cosmetic_Consultant` (`cosmetic_ssn`),
  ADD CONSTRAINT `Cosmetic_Product_Recommendation_ibfk_3` FOREIGN KEY (`product_id`) REFERENCES `Product` (`product_id`);

--
-- Constraints for table `Customer`
--
ALTER TABLE `Customer`
  ADD CONSTRAINT `Customer_ibfk_1` FOREIGN KEY (`cosmetic_ssn`) REFERENCES `Cosmetic_Consultant` (`cosmetic_ssn`);

--
-- Constraints for table `PharmacyEmployee`
--
ALTER TABLE `PharmacyEmployee`
  ADD CONSTRAINT `PharmacyEmployee_ibfk_1` FOREIGN KEY (`pharmacy_id`) REFERENCES `Pharmacy` (`pharmacy_id`);

--
-- Constraints for table `Product`
--
ALTER TABLE `Product`
  ADD CONSTRAINT `Product_ibfk_1` FOREIGN KEY (`manufacturing_company_id`) REFERENCES `Manufacturing_Company` (`manufacturing_company_id`) ON DELETE CASCADE ON UPDATE CASCADE;

--
-- Constraints for table `Sell`
--
ALTER TABLE `Sell`
  ADD CONSTRAINT `Sell_ibfk_1` FOREIGN KEY (`pharmacy_id`) REFERENCES `Pharmacy` (`pharmacy_id`),
  ADD CONSTRAINT `Sell_ibfk_2` FOREIGN KEY (`product_id`) REFERENCES `Product` (`product_id`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
```
