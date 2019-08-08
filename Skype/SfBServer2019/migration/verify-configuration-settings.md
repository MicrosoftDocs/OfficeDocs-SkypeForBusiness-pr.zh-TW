---
title: 驗證配置設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以在中央管理儲存位置所在的內部電腦上執行商務用 Skype Server 2019 CsManagementStoreReplicationStatus Cmdlet, 或在任何情況下, 驗證將配置資訊複製到 Edge 伺服器。已加入網域的電腦, 其中安裝了商務用 Skype Server 2019 核心元件 (OcsCore .msi)。
ms.openlocfilehash: 5beb3c80bbc4c2f9a73fe68b9d99d7752598c680
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241725"
---
# <a name="verify-configuration-settings"></a>驗證配置設定

您可以在中央管理儲存位置所在的內部電腦上執行商務用 Skype Server 2019 **CsManagementStoreReplicationStatus** Cmdlet, 以驗證將配置資訊複製到 Edge 伺服器, 或在已安裝商務用 Skype Server 2019 核心元件 (OcsCore) 的任何加入網域的電腦上。 
  
初始結果可能會指出狀態為「False」, 而不是「True」以進行複製。 如果是, 請執行**CsManagementStoreReplication** Cmdlet, 並允許複製完成時間, 然後再次執行**CsManagementStoreReplicationStatus** 。 
  

