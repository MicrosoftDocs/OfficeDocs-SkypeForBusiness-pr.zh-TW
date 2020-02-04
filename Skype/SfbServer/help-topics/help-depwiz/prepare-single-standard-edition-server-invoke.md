---
title: 準備單一 Standard Edition Server (叫用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在 [執行命令] 頁面上，安裝 SQL Server Express 和設定來充當中央管理儲存區的工作，可以在工作窗格中查看。 根據預設，會建立名稱為「RTC」的 SQL Server 資料庫實例。 您也可以建立防火牆規則，以允許伺服器和用戶端與資料庫和實例進行通訊的入站和輸出存取。 工作完成後，您可以從下拉式清單中選取記錄檔。 記錄檔稱為 [引導本機電腦]。 選取記錄檔後，按一下 [查看記錄]。 檢查記錄檔，查看是否有任何錯誤和警告。 當您準備好要繼續時，請按一下 [完成]。 您現在應該使用拓撲建立器定義拓撲（如果您尚未這麼做）。
ms.openlocfilehash: 729bdacffff09876272e45a34377ced950e88ebf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700808"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>準備單一 Standard Edition Server (叫用)
 
在 [**執行命令**] 頁面上，安裝 SQL Server Express 和設定來充當中央管理儲存區的工作，可以在工作窗格中查看。 根據預設，會建立名稱為「RTC」的 SQL Server 資料庫實例。 您也可以建立防火牆規則，以允許伺服器和用戶端與資料庫和實例進行通訊的入站和輸出存取。 工作完成後，您可以從下拉式清單中選取記錄檔。 記錄檔稱為 [**引導本機電腦**]。 選取記錄檔後，按一下 [**查看記錄**]。 檢查記錄檔，查看是否有任何錯誤和警告。 當您準備好要繼續時，請按一下 **[完成]。** 您現在應該使用拓撲建立器定義拓撲（如果您尚未這麼做）。
  
> [!IMPORTANT]
> 安裝 SQL Server Express 可能需要一些時間才能完成。 在安裝期間，螢幕或工作窗格中不會顯示任何進度。 若要監視安裝，您應該使用 Windows 工作管理員，尋找 MSIExec 進程以及 SQL Server 的安裝檔案。 如此一來，您就可以查看安裝狀態，並確定安裝繼續進行。 您可能需要15分鐘以上的時間才能完成安裝 SQL Server 實例，這取決於此說明主題範圍以外的因素。 
  

