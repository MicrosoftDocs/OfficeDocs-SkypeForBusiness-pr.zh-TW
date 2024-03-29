---
title: 準備單一 Standard Edition Server (叫用)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: 在 [執行命令] 頁面上，您可以在工作窗格中查看安裝 SQL Server Express 和設定以充當中央管理存放區的工作。 根據預設，會建立名為 RTC 的 SQL Server 型資料庫實例。 也會建立防火牆規則，允許輸入和輸出存取，讓伺服器和用戶端能夠與資料庫及執行個體進行通訊。 工作完成之後，您可以從下拉式清單選取記錄檔。 記錄檔名稱為 [啟動程序本機電腦]。 選取記錄檔之後，請按一下 [檢視記錄檔]。 請檢閱記錄檔中是否有任何錯誤和警告。 準備好可以繼續時，按一下 [完成]。 您現在應該使用拓撲產生器來定義拓撲（如果尚未這麼做）。
ms.openlocfilehash: 3aa74d3255d537cc6a9f9d6942f5fccae7bee1b3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385201"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>準備單一 Standard Edition Server (叫用)
 
在 [**執行命令**] 頁面上，您可以在工作窗格中查看安裝 SQL Server Express 和設定以充當中央管理存放區的工作。 根據預設，會建立名為 RTC 的 SQL Server 型資料庫實例。 也會建立防火牆規則，允許輸入和輸出存取，讓伺服器和用戶端能夠與資料庫及執行個體進行通訊。 工作完成之後，您可以從下拉式清單選取記錄檔。 記錄檔名稱為 **[啟動程序本機電腦]**。 選取記錄檔之後，請按一下 **[檢視記錄檔]**。 請檢閱記錄檔中是否有任何錯誤和警告。 準備好可以繼續時，按一下 **[完成]**。 您現在應該使用拓撲產生器來定義拓撲（如果尚未這麼做）。
  
> [!IMPORTANT]
> 安裝 SQL Server Express 可能需要一些時間才能完成。 在安裝期間，畫面或工作窗格上不會看到任何進度。 若要監視安裝，您應該使用 Windows 的任務管理員，並尋找 SQL Server 的 MSIExec 處理常式和安裝檔案。 如此您可以檢視安裝的狀態，並確定安裝正在進行中。 取決於此說明主題範圍以外的因素，安裝 SQL Server 實例最多可能需要15分鐘的時間才能完成。 
  

