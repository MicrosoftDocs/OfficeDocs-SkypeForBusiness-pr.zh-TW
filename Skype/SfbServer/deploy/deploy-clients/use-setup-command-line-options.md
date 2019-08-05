---
title: 在商務用 Skype 用戶端使用 Setup 命令列選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '摘要: 瞭解 Office 設定中的 setup.exe 命令列操作。'
ms.openlocfilehash: 2eee24f9ae79ed2f73e23c68883f2552902fb672
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193822"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>在商務用 Skype 用戶端使用 Setup 命令列選項
 
**摘要:** 瞭解 Office 設定中的 setup.exe 命令列操作。
  
Setup.exe 命令列適用于 Office 設定中的極少作業。 您通常會使用 Office 自訂工具和 Config.xml 檔案來進行產品設定和功能自訂, 而不是使用 [設定] 命令列選項。
  
Office Setup.exe 命令列會辨識下表所述的命令列選項。
  
**Office 設定命令列選項**

|**設定命令列選項**|**說明**|
|:-----|:-----|
|/admin  <br/> |執行 Office 自訂工具來建立安裝程式自訂檔 (.msp 檔案)。  <br/> |
|/adminfile [path]  <br/> |將指定的安裝程式自訂檔案套用到安裝。 您可以指定特定自訂檔案 (.msp 檔案) 或儲存自訂檔案的資料夾路徑。  <br/> |
|/config [path]  <br/> |指定安裝程式在安裝期間使用的 Config.xml 檔案。 使用/config 選項指定您針對商務用 Skype 安裝所自訂的 Config.xml 檔案, 例如:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |與已修改的 Config.xml 檔案搭配使用, 可在維護模式中執行安裝程式, 並變更現有的 Office 安裝。 例如, 您可以使用/modify 選項來新增或移除商務用 Skype 功能。  <br/> |
|/repair Skype  <br/> |從使用者的電腦執行安裝程式, 以修復商務用 Skype。  <br/> |
|/uninstall Skype  <br/> |執行安裝程式, 從使用者的電腦中移除商務用 Skype。  <br/> |
   


