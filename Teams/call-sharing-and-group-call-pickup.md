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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共用和群組呼叫代答功能可讓使用者與同事共用來電，讓使用者可以在使用者無法使用時接聽來電。
ms.openlocfilehash: 88c8d41eb0cf58413df995274bb9accd50b897c9
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637825"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams 中的通話共用和群組通話代答

Microsoft Teams 的通話共用和群組呼叫代答功能可讓使用者與同事共用來電，讓同事可以接聽使用者無法使用時發生的通話。

與其他通話共用形式 (例如呼叫轉轉或同時撥打) 相比，群組呼叫代答對收件者影響較小，因為使用者可以設定使用者想要透過音訊和視覺通知 (僅透過 Teams App) 中的視覺或橫幅收到來電通知的方式，而且他們可以決定是否要接聽。

若要與其他人共用通話，使用者會建立通話群組，並新增想要共用通話的使用者。 接著，他們選擇同時響鈴或轉場設定。 詳細 [資料請參閱 Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 中的呼叫轉轉和同時撥打。 請注意，行動裝置只有在設定為橫幅和鈴聲時，才能收到通知。

> [!IMPORTANT]
> 使用者、通話群組擁有者和通話群組的成員必須進入 Teams Only 部署模式。 有關 Teams 部署模式的詳細資訊，請參閱瞭解 Microsoft Teams 和商務用 [Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要授權

使用者必須獲得 Microsoft Teams Phone System 授權，才能設定及使用通話共用和群組呼叫代答。 有關授權模型的其他詳細資料，請參閱以下說明您取得[手機系統功能。](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)

## <a name="configure-group-call-pickup"></a>設定群組通話代答

若要設定群組呼叫代答，使用者會先設定通話群組 (這與安全性群組或 Microsoft 365 群組) 不同，然後新增想要共用通話的使用者。 接著，他們選擇同時撥打或呼叫前轉設定。 有關詳細資訊和逐步程式，請參閱 Teams 中的呼叫 [轉譯和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

通話群組建立和通知喜好設定是使用者導向的功能;系統管理員不需要為使用者設定這些功能。 無法從安全性群組或 Microsoft 365 群組建立通話群組;他們必須在 Teams 中建立。

系統管理員應透過使用者的 **TeamsCallingPolicy AllowCallGroups 設定啟用** 通話群組。 系統管理員也可以透過 Teams 系統管理入口網站啟用這項功能。  此外，已設定的使用者也可以直接透過用戶端設定其通話群組。 系統管理員或使用者無法彼此封鎖組塊，但 Teams 系統管理入口網站和 Teams 用戶端應該在這兩個地方正確顯示此關係。 

重要：當系統管理員在使用者 (開啟通話群組後關閉通話群組，且呼叫群組關係已) 時，系統管理員必須清除 Teams 系統管理中心中的使用者的通話群組關係，以避免不正確的通話路由。 

## <a name="limitations"></a>限制

租使用者最多可以包含 32，768 個通話群組。 每個通話群組最多可以有 25 個使用者。 

## <a name="more-information"></a>詳細資訊

[Teams 中的呼叫轉轉和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
