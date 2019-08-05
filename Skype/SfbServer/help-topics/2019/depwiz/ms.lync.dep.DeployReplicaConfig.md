---
title: 安裝本機配置存儲區 (設定)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要開始安裝將保留中央管理儲存區的本機唯讀複本的資料庫, 您可以在從已安裝和設定的中央的 [拓撲建立器] 中, 選取 [使用拓撲建立器] 來檢索已定義的設定管理儲存, 或從其他媒體讀取已定義的配置。 針對貴組織內部網路上的電腦, 選取 [從中央管理儲存庫自動取得設定]。
ms.openlocfilehash: b4249f4968c51fb901e612b2414bb2c6921be40c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193514"
---
# <a name="install-local-configuration-store-invoke-configure"></a>安裝本機配置存儲區 (設定)
 
若要開始安裝將保留中央管理儲存區的本機唯讀複本的資料庫, 您可以在從已安裝和設定的中央的 [拓撲建立器] 中, 選取 [使用拓撲建立器] 來檢索已定義的設定管理儲存, 或從其他媒體讀取已定義的配置。 針對貴組織內部網路上的電腦, 選取 **[從中央管理儲存庫自動取得**設定]。
  
如果您要在 Edge 伺服器上安裝中央管理儲存體的複本, 您可以選取以從便攜媒體 (例如 USB 快閃磁碟機、USB 硬碟磁碟機、cd-rom 或其他媒體) 讀取設定檔的匯出複本。 
  
> [!IMPORTANT]
> 如果您要在 Edge 伺服器上安裝本機配置存放區, 則配置資訊必須是從中央管理存儲匯出的格式, 方法是執行 Windows PowerShell Cmdlet:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
選取適當的選項之後, 請按 **[下一步]**。
  

