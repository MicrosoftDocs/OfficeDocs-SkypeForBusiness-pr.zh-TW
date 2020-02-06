---
title: 驗證組態設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以在中央管理儲存位置所在的內部電腦上執行商務用 Skype Server 2019 CsManagementStoreReplicationStatus Cmdlet，或在任何情況下，驗證將配置資訊複製到 Edge 伺服器。已加入網域的電腦，其中安裝了商務用 Skype Server 2019 核心元件（OcsCore .msi）。
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812751"
---
# <a name="verify-configuration-settings"></a>驗證組態設定

您可以在中央管理儲存位置所在的內部電腦上執行商務用 Skype Server 2019 **CsManagementStoreReplicationStatus** Cmdlet，或在已安裝商務用 Skype Server 2019 核心元件（OcsCore .msi）的任何加入網域的電腦上，執行驗證將配置資訊複製到 Edge 伺服器。 
  
初始結果可能會指出狀態為「False」，而不是「True」以進行複製。 如果是，請執行**CsManagementStoreReplication** Cmdlet，並允許複製完成時間，然後再次執行**CsManagementStoreReplicationStatus** 。 
  

