---
title: 通話共用和群組來電接聽
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共用和群組通話挑選讓使用者與同事共用來電，以便在使用者無法使用時，可以捕獲通話。
ms.openlocfilehash: 727e3a4c3627e38722182bc1d6ad1f4e435d95a4
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780782"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>在 Microsoft 團隊中呼叫共用與群組通話挑選

Microsoft 團隊的呼叫共用與群組呼叫功能可讓使用者與同事共用來電，讓同事可以接聽使用者無法使用的通話。

群組呼叫對於收件者的電話與其他形式的呼叫共用（例如來電轉接或同時撥打），因為使用者可以設定收到來電通知的方式（透過音訊和視覺通知、僅限 visual 或橫幅在團隊應用程式中），他們可以決定是否要回復。

若要與其他人共用通話，使用者可以建立通話群組，並新增他們要與其通話共用的使用者。 然後，選擇同時撥打或轉寄設定。 如需詳細資訊，請參閱[在小組中來電轉接及同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

> [!IMPORTANT]
> 使用者、通話群組擁有者，以及通話群組的成員，都必須在 [只有小組] 部署模式中。 如需有關團隊部署模式的詳細資訊，請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要授權

使用者必須是啟用企業語音，才能設定及使用通話共用和群組通話。 如需授權模型的其他詳細資料，請參閱[Microsoft 團隊適用的 Office 365 授權](office-365-licensing.md)。

## <a name="configure-group-call-pickup"></a>設定群組呼叫挑選

若要設定 [群組呼叫挑選]，使用者必須先設定通話群組（這與安全性群組或 Office 365 群組不同），然後再新增他們要與其共用通話的使用者。 然後，選擇 [同時撥打] 或 [來電轉接] 設定。 如需詳細資訊和逐步程式，請參閱[在小組中來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

通話群組建立和通知喜好設定是使用者驅動的功能;系統管理員不需要為使用者設定這些功能。 無法從安全性群組或 Microsoft 365 群組建立通話群組;它們必須在 [團隊] 中建立。

系統管理員應該透過使用者的 [ **TeamsCallingPolicy AllowCallGroups** ] 設定來啟用呼叫群組。 系統管理員也可以透過 [團隊管理入口網站] 啟用此。  此外，已設定的使用者也可以直接透過用戶端設定通話群組。 系統管理員或使用者不能封鎖彼此的設定，但是團隊管理員入口網站和團隊用戶端應該在這兩個位置中正確顯示這種關聯性。 

重要：當系統管理員關閉使用者的呼叫群組之後（已開啟並設定通話群組關聯），系統管理員必須清除小組系統管理中心中使用者的通話群組關聯，以避免呼叫路由不正確。 

## <a name="limitations"></a>有限

租使用者最多可以包含32768呼叫群組。 每個通話群組中最多可以有25個使用者。 

## <a name="more-information"></a>詳細資訊

[在小組中來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
