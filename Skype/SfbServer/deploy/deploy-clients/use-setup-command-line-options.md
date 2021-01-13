---
title: 搭配商務用 Skype 用戶端使用安裝程式命令列選項
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要：瞭解 Office 安裝中的 Setup.exe 命令列作業。
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837203"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>搭配商務用 Skype 用戶端使用安裝程式命令列選項
 
**摘要：** 深入瞭解 Office 安裝中的 Setup.exe 命令列作業。
  
Setup.exe 命令列將用於 Office 安裝中非常少的作業。 您通常會使用 Office 自訂工具和 Config.xml 檔案進行產品安裝和功能自訂，而不是使用安裝程式的命令列選項。
  
Office Setup.exe 命令列會識別下表所述的命令列選項。
  
**Office 安裝程式 Command-Line 選項**

|**安裝 Command-Line 選項**|**描述**|
|:-----|:-----|
|/admin  <br/> |執行 Office 自訂工具，以建立安裝程式自訂檔案 (.msp 檔案)。  <br/> |
|/adminfile [path]  <br/> |將指定的安裝程式自訂檔案套用至安裝。您可以指定特定自訂檔案 (.msp 檔案) 的路徑，或是儲存自訂檔案的資料夾路徑。  <br/> |
|/config [path]  <br/> |指定在安裝過程中，安裝程式所使用的 Config.xml 檔案。 使用 [/config] 選項指定您為商務用 Skype 安裝所自訂的 Config.xml 檔案，例如：  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |與修改的 Config.xml 檔案搭配使用，即可在維護模式中執行安裝程式，並對現有的 Office 安裝進行變更。 例如，您可以使用/modify 選項來新增或移除商務用 Skype 功能。  <br/> |
|/repair Skype  <br/> |從使用者的電腦執行安裝程式，以修理商務用 Skype。  <br/> |
|/uninstall Skype  <br/> |執行安裝程式以從使用者的電腦中移除商務用 Skype。  <br/> |
   


