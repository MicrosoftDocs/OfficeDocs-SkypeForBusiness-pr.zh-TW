---
title: 準備單一 Standard Edition Server (叫用)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在 [執行命令] 頁面上，您可以在工作窗格中查看安裝 SQL Server Express 和設定以充當中央管理存放區的工作。 根據預設，會建立名為 RTC 的 SQL Server 型資料庫實例。 也會建立防火牆規則，允許輸入和輸出存取，讓伺服器和用戶端能夠與資料庫及執行個體進行通訊。 工作完成之後，您可以從下拉式清單選取記錄檔。 記錄檔名稱為 [啟動程序本機電腦]。 選取記錄檔之後，請按一下 [檢視記錄檔]。 請檢閱記錄檔中是否有任何錯誤和警告。 準備好可以繼續時，按一下 [完成]。 您現在應該使用拓撲產生器來定義拓撲（如果尚未這麼做）。
ms.openlocfilehash: 0a1ebca35fc2d09af3dcadab8bc0d4ef43fc2893
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764201"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>準備單一 Standard Edition Server (叫用)
 
在 [**執行命令**] 頁面上，您可以在工作窗格中查看安裝 SQL Server Express 和設定以充當中央管理存放區的工作。 根據預設，會建立名為 RTC 的 SQL Server 型資料庫實例。 也會建立防火牆規則，允許輸入和輸出存取，讓伺服器和用戶端能夠與資料庫及執行個體進行通訊。 工作完成之後，您可以從下拉式清單選取記錄檔。 記錄檔名稱為 **[啟動程序本機電腦]**。 選取記錄檔之後，請按一下 **[檢視記錄檔]**。 請檢閱記錄檔中是否有任何錯誤和警告。 準備好可以繼續時，按一下 **[完成]**。 您現在應該使用拓撲產生器來定義拓撲（如果尚未這麼做）。
  
> [!IMPORTANT]
> 安裝 SQL Server Express 可能需要一些時間才能完成。 在安裝期間，畫面或工作窗格上不會看到任何進度。 若要監視安裝，您應該使用 Windows 的任務管理員，並尋找 SQL Server 的 MSIExec 處理常式和安裝檔案。 如此您可以檢視安裝的狀態，並確定安裝正在進行中。 取決於此說明主題範圍以外的因素，安裝 SQL Server 實例最多可能需要15分鐘的時間才能完成。 
  

