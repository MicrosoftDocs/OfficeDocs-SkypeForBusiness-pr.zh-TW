---
title: 通話共用和群組來電接聽
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共用和群組呼叫代答功能可讓使用者與同事共用來電，讓使用者在無法使用時可以接聽來電。
ms.openlocfilehash: 7f9e24114d47ff331ad36a653a2bbe0f31fcad08
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014127"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>通話共用和群組通話代答Microsoft Teams

通話共用和群組呼叫代答功能Microsoft Teams讓使用者與同事共用來電，讓同事可以接聽使用者無法使用時發生的通話。

與其他通話共用形式 (例如呼叫轉轉或同時撥打) 相比，群組呼叫代答對收件者影響較小，因為使用者可以設定想要透過 Teams App) 中的音訊和視覺通知、僅視覺或橫幅收到來電通知的方式 (，而且他們可以決定是否接聽。

若要與其他人共用通話，使用者會建立通話群組，並新增想要共用通話的使用者。 接著，他們選擇同時響鈴或轉場設定。 請參閱[呼叫轉轉和同時撥打Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)詳細資料。 請注意，行動裝置只有在設定為橫幅和鈴聲時，才能收到通知。

> [!IMPORTANT]
> 使用者、通話群組擁有者和通話群組的成員必須Teams部署模式。 有關部署模式Teams，請參閱瞭解Microsoft Teams[及商務用 Skype互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>需要授權

使用者必須獲得授權Microsoft Teams 電話系統才能設定及使用通話共用和群組呼叫代答。 有關授權模型的其他詳細資料，請參閱以下說明您取得[授權電話系統。](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

## <a name="configure-group-call-pickup"></a>設定群組通話代答

若要設定群組呼叫代答，使用者會先設定通話群組 (這與安全性群組或 Microsoft 365 群組) 不同，然後新增想要共用通話的使用者。 接著，他們選擇同時撥打或呼叫前轉設定。 如要詳細資訊和逐步程式，請參閱在 Teams 中呼叫轉[Teams。](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

通話群組建立和通知喜好設定是使用者導向的功能;系統管理員不需要為使用者設定這些功能。 無法從安全性群組或群組建立Microsoft 365群組;它們必須在 Teams 中Teams。

系統管理員應透過使用者的 **TeamsCallingPolicy AllowCallGroups 設定啟用** 通話群組。 系統管理員也可以透過系統管理入口網站Teams此功能。  此外，已設定的使用者也可以直接透過用戶端設定其通話群組。 系統管理員或使用者無法彼此封鎖該組Teams，但系統管理入口網站Teams用戶端應該能正確地在這兩個地方顯示此關係。 

重要：當系統管理員在使用者 (開啟後關閉通話群組，且呼叫群組關係已配置) 時，系統管理員必須清除 Teams 系統管理中心中的使用者的通話群組關係，以避免不正確的通話路由。 

## <a name="limitations"></a>限制

每個已配置的通話群組最多可以有 25 個使用者或 32，768 個字元。 

## <a name="more-information"></a>詳細資訊

[呼叫轉譯和同時撥打Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
