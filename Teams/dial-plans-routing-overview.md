---
title: 撥號對應表和路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Microsoft Teams 中的撥號對應表和路由
ms.openlocfilehash: 3fc29dc27f1f3863ed313b75c8ef977cd27a6231
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551897"
---
# <a name="overview"></a>概觀

本節中的文章說明 Microsoft Teams 中的撥號對應和通話路由。 

- [什麼是撥號對應表](what-are-dial-plans.md)
- [建立和管理撥號對應表](create-and-manage-dial-plans.md)
- [將通話路由至未指派的 Nu 問題](routing-calls-to-unassigned-numbers.md)

本節中的文章適用于連線到公用交換電話網路的所有選項 (PSTN) ：通話方案、電信業者連線、Teams Phone Mobile 和直接路由。 如需所有 PSTN 連線選項的詳細資訊，請參閱 [PSTN 連線選項](pstn-connectivity.md)。

如果您選擇 [通話方案]、[電信業者連線] 或 [Teams Phone Mobile]，則大部分的通話路由是由 Microsoft 或您的提供者負責。 不過，直接路由需要額外步驟來設定通話路由。 

若是直接路由，您必須指定語音路由，並將語音路由原則指派給使用者，藉此設定通話路由。 您可以在主幹層級設定撥號對應表，以確保可與會話框線控制器 (SBC) 互通性。 如需詳細資訊，請參閱設定 [直接路由的語音路由](direct-routing-voice-routing.md)、 [管理語音路由原則](manage-voice-routing-policies.md) 和 [翻譯電話號碼](direct-routing-translate-numbers.md)。

請注意，您可以將直接路由線上語音路由原則指派給通話方案和運算子連線使用者。 舉例來說，您可能會想要這樣做，讓使用者能夠直接撥入通話中心。 您可以設定直接路由主幹到話務中心。

例如，如果使用者有通話方案授權，該使用者的撥出電話會自動透過 Microsoft 通話方案 PSTN 基礎結構路由。 如果您設定並指派直接路由線上語音路由原則給使用者，系統會檢查使用者的撥出電話，以判斷撥號是否符合線上語音路由原則中定義的號碼模式。 如果有相符專案，通話會透過直接路由主幹路由路由傳送。 如果沒有相符的專案，通話會透過通話方案 PSTN 基礎結構路由。

如需詳細資訊，請參閱 [直接路由語音路由原則考慮](direct-routing-voice-routing.md#voice-routing-policy-considerations)。



