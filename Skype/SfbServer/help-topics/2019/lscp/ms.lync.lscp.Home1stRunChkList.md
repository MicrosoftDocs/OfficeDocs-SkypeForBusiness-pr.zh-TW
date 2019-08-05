---
title: 商務用 Skype Server 控制台的初次執行檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: 歡迎使用商務用 Skype Server 的 [控制台], 它是用來管理和管理商務用 Skype Server 的 web 使用者介面。 您可以使用控制台來執行過去只能透過 Microsoft 管理主控台執行的管理工作類型。
ms.openlocfilehash: 1f3241d854a402036832468594c2e399eb7b1617
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190897"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>商務用 Skype Server 控制台的初次執行檢查清單

歡迎使用商務用 Skype Server 的 [控制台], 它是用來管理和管理商務用 Skype Server 的 web 使用者介面。 您可以使用控制台來執行過去只能透過 Microsoft 管理主控台執行的管理工作類型。

在您部署商務用 Skype Server 之後, 我們強烈建議您執行一些重要的工作。 這些工作包含您可能在部署期間已執行過的初始設定步驟，其他則是針對您在部署期間的設定或預設值進行細分或修改。 本主題中描述的其他工作會驗證您在部署過程中所進行的設定。

> [!NOTE]
> 在開始執行下表中的工作之前，請確認您行使正確的使用者權利與權限，並以適當的角色登入，如同〈[Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)〉的〈角色和範圍〉一節的描述。

## <a name="first-run-checklist"></a>第一次執行檢查清單

我們強烈建議您複習本主題中提到的工作, 然後在您的組織中執行適當的程式以進行部署。

|**工作**|**控制台群組**|**文件**|
|:-----|:-----|:-----|
|確認您安裝在拓撲中的服務如預期地執行中。  <br/> |**拓撲** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|針對商務用 Skype Server 啟用使用者。 或者, 如果從舊版遷移, 請將使用者移至商務用 Skype Server。  <br/> |**使用者** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|如果您已部署，或想要部署企業語音，請設定 SIP 主幹連線，以啟用對公用交換電話網路 (PSTN) 的連線。  <br/> |**語音路由** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|如果您部署了企業語音，請確認企業語音路由設定。  <br/> |**語音路由** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|如果您部署了封存伺服器，請確認封存原則和設定符合您組織的規範需要。  <br/> |**監控和封存** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|如果您部署了監控伺服器，請檢視監控伺服器報告，以便檢視使用方式和診斷資訊。  <br/> |**首頁** <br/> |[在商務用 Skype Server 中管理健康情況與監控](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


