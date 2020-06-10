1. Создание таблиц БД:

CREATE TABLE [dbo].ElementSet (
    [Id]   INT           IDENTITY (1, 1) NOT NULL,
    [Name] NVARCHAR (50) NULL,
    PRIMARY KEY CLUSTERED (Id ASC)
);
CREATE TABLE [dbo].PetSet (
    [Id]        INT            IDENTITY (1, 1) NOT NULL,
    [Name]      NVARCHAR (MAX) NOT NULL,
    [ElementId] INT            NOT NULL,
    [Slot1]     INT            NOT NULL,
    [Slot2]     INT            NOT NULL,
    [Slot3]     INT            NOT NULL,
    [Slot4]     INT            NOT NULL,
    PRIMARY KEY CLUSTERED (Id ASC)
);
CREATE TABLE [dbo].TalismanTypeSet (
    [Id]   INT           IDENTITY (1, 1) NOT NULL,
    [Name] NVARCHAR (50) NOT NULL,
    PRIMARY KEY CLUSTERED (Id ASC)
);
CREATE TABLE [dbo].TalismanSet (
    [Id]             INT IDENTITY (1, 1) NOT NULL,
    [TalismanTypeId] INT NOT NULL,
    [Lvl]            INT NOT NULL,
    [Grass]          INT NOT NULL,
    [Stone]          INT NOT NULL,
    [Fish]           INT NOT NULL,
    [ESearch]        INT NOT NULL,
    [TSearch]        INT NOT NULL,
    [WSearch]        INT NOT NULL,
    PRIMARY KEY CLUSTERED (Id ASC)
);
CREATE TABLE [dbo].ElementColorSet (
    [Id]        INT IDENTITY (1, 1) NOT NULL,
    [ElementId] INT NOT NULL,
    [ColorId]   INT NOT NULL,
    [Grass]     INT NOT NULL,
    [Stone]     INT NOT NULL,
    [Fish]      INT NOT NULL,
    [ESearch]   INT NOT NULL,
    [TSearch]   INT NOT NULL,
    [WSearch]   INT NOT NULL,
    PRIMARY KEY CLUSTERED (Id ASC)
);

2. Вызовы библиотеки:

new PetsReitList().GetPetsReitList(lvl, color);