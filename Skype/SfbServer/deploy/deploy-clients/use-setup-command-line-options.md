---
title: 搭配商務用 Skype 用戶端使用安裝程式命令列選項
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要：瞭解 Office 安裝中 Setup.exe 命令列作業。
ms.openlocfilehash: a70d6a2c905f40f61d0cdbdcc5dd92a4b9bfdf75
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396065"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>搭配商務用 Skype 用戶端使用安裝程式命令列選項
 
**總結：** 深入瞭解 Office 安裝中的 Setup.exe 命令列作業。
  
Setup.exe 命令列將用於 Office 安裝程式中非常少的作業。 您通常會使用 Office 自訂工具和 Config.xml 檔案進行產品安裝和功能自訂，而不是使用安裝程式命令列選項。
  
Office Setup.exe 命令列會識別下表所述的命令列選項。
  
**Office 安裝 Command-Line 選項**

|**安裝 Command-Line 選項**|**描述**|
|:-----|:-----|
|/admin  <br/> |執行 Office 自訂工具，以建立安裝程式自訂檔案 (.msp 檔案)。  <br/> |
|/adminfile [path]  <br/> |將指定的安裝程式自訂檔案套用至安裝。您可以指定特定自訂檔案 (.msp 檔案) 的路徑，或是儲存自訂檔案的資料夾路徑。  <br/> |
|/config [path]  <br/> |指定在安裝過程中，安裝程式所使用的 Config.xml 檔案。 使用 [/config] 選項可指定您針對商務用 Skype 安裝自訂的 Config.xml 檔案，例如：`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |與修改的 Config.xml 檔案搭配使用，即可在維護模式中執行安裝程式，並對現有的 Office 安裝進行變更。 例如，您可以使用/modify 選項來新增或移除商務用 Skype 功能。  <br/> |
|/repair Skype  <br/> |從使用者的電腦執行安裝程式，以修復商務用 Skype。  <br/> |
|/uninstall Skype  <br/> |執行安裝程式以從使用者的電腦中移除商務用 Skype。  <br/> |
   


