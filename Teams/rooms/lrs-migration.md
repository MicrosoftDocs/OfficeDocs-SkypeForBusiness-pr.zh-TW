---
title: 將 Lync 會議室系統裝置遷移到 Microsoft Teams 會議室
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 請閱讀本主題，瞭解如何將 Lync Room System 裝置Microsoft Teams 會議室軟體。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aae146767f66327e5678956a14dfe72d957a8164
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503510"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>將 Lync 會議室系統 (LRS) 裝置Microsoft Teams 會議室

Lync Room System (LRS) 裝置與 Skype 會議室系統版本 1 (SRS v1) 軟體于[2018 年 10 月 9](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)日終止支援。 這表示 Skype 會議室系統 v1 軟體將不再取得任何產品更新或修正。 如果客戶的裝置是使用 Skype 會議室系統 v1 軟體的 Lync Room System 裝置，建議您將其裝置升級至「Microsoft Teams 會議室」。

Microsoft Teams 會議室軟體可Microsoft Teams，商務用 Skype Server所有支援裝置上的會議和Microsoft Teams 會議室線上服務。

您的現有裝置 **在** 會議室系統 v1 軟體支援結束後Skype繼續使用。 不過，如果此軟體發生軟體錯誤，需要 Microsoft 發行修正程式，則不支援此修正程式。 SRS v1 會使用 TLS 1.0/ 1.1，Microsoft 未來將會以 TLS 1.0/ 1.1 來代用。 您可以深入瞭解如何 [準備 TLS 1.0/1.1 棄用](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)。 

## <a name="which-devices-are-affected"></a>哪些裝置受到影響？

以下是受此變更影響的裝置清單：

- Cresron RL
- [Cresron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [SMART Room 系統](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>升級選項

有多種選項可升級 Lync 會議室系統至下一代Microsoft Teams 會議室。

### <a name="crestron-hardware-trade-in-program"></a>Cresron 硬體折中計畫

Cresron 會針對所有非Crsron Lync Room System 客戶 (例如 Smart 或 Polycom LRS) 提供 [Crsron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) 系統的升級或同等) 。 請在這裡查看此計畫 [詳細資料，](https://support.crestron.com/app/answers/answer_view/a_id/1000220) 或 <!-- For details, -->[電子郵件](mailto:lrsupgrade@crestron.com) Cresron LRS 支援。  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>將 Cresron RL2 升級至 Microsoft Teams 會議室

現有的Crsron RL2 (也稱為Crsron RL200) 客戶可以取得升級套件，以將目前的 RL2 升級為 RL3，每個裝置的成本最低。 請在這裡查看此計畫 [詳細資料](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。

### <a name="smart-room-systems-upgrade"></a>SMART Room Systems 升級

針對 SMART LRS 客戶，除了使用Crsron 硬體折讓方案之外，SMART 也正在努力提供升級至 Microsoft Teams 會議室。 此升級由 SMART Technologies Inc. 在產品支援下提供給客戶。 請在這裡查看更多 [有關此資訊](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)。


## <a name="what-should-you-do"></a>您應該怎麼做？

我們建議您使用上述升級選項Microsoft Teams 會議室在 TLS 1.0/1.1 之前更新 Lync Room System 裝置。 此外，您也可以考慮將現有裝置取代為經過認證的新裝置，Microsoft Teams 會議室。 請參閱[會議室裝置](https://aka.ms/roomdevices)以瞭解詳細資料，並查看Microsoft Teams 會議室[需求](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  


> [!NOTE]
> Microsoft Teams 會議室軟體支援自 2018 年 12 月 14 日起使用 App 版本 4.0.64.0 的 TLS 1.2 通訊協定。 對於內部部署客戶，Microsoft Teams 會議室 的 TLS 1.2 啟用通訊時，需要 商務用 Skype Server 2015 累積更新 9 (CU9) 或 商務用 Skype Server 2019 累積更新 1 (CU1) 。 變更不應影響線上商務用 Skype，因為用戶端變更是向前和向後相容。