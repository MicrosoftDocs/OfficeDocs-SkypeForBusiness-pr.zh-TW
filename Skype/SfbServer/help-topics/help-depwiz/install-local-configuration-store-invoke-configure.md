---
title: 安裝本機設定存放區叫用 (設定)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 若要開始安裝儲存中央管理存放區之本機唯讀副本的資料庫，請選取 [從已安裝及已設定的中央管理存放區中使用拓撲產生器所發佈的定義設定]，或從其他媒體讀取已定義的設定。 針對組織內部網路上的機器，選取 [自動從中央管理存放區取回設定]。
ms.openlocfilehash: a2e0efdc33fdfb6070b445c0a1e7868dab0f0ff2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411786"
---
# <a name="install-local-configuration-store-invoke-configure"></a>安裝本機設定存放區叫用 (設定)
 
若要開始安裝儲存中央管理存放區之本機唯讀副本的資料庫，請選取 [從已安裝及已設定的中央管理存放區中使用拓撲產生器所發佈的定義設定]，或從其他媒體讀取已定義的設定。 針對組織內部網路上的機器，選取 **[自動從中央管理存放區取回** 設定]。
  
若要在 Edge Server 上安裝中央管理存放區的複本，請選取從便攜媒體（例如 USB 快閃記憶體磁片磁碟機、USB 硬碟、CD-ROM 或其他媒體）讀取設定檔的匯出副本。 
  
> [!IMPORTANT]
> 若要在 Edge Server 上安裝本機設定存放區，則設定資訊必須採用從中央管理存放區匯出的格式，方法是執行 Windows PowerShell Cmdlet：`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
選取適當的選項後，請按 **[下一步]**。
  

