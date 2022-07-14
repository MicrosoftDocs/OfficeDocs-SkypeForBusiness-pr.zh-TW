---
title: 通話共用和群組來電接聽
author: CarolynRowe
ms.author: crowe
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
description: 通話共用和群組通話接聽可讓使用者與同事共用來電，以便在使用者無法使用時擷取來電。
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789948"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams 中的通話共用和群組通話接聽

Microsoft Teams 的通話共用和群組通話接聽功能可讓使用者與同事共用來電，讓同事可以接聽使用者無法接聽的電話。

比起其他形式的通話共用 (，例如來電轉接或同時撥打) ，接聽群組通話對收件者干擾較小，因為使用者可以設定如何透過 Teams 應用程式) 中的音訊和視覺通知、僅限視覺效果或橫幅收到共用來電 (，而且他們可以決定是否要接聽。

若要與其他人共用通話，使用者會建立通話群組，並新增他們要與之共用通話的使用者。 然後他們選擇同時響鈴或轉寄設定。 如需詳細資料，請參閱 [Teams 中的來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 。 請注意，行動裝置只有在設定為橫幅和鈴聲時才會收到通知。

> [!IMPORTANT]
> 使用者、通話群組擁有者及通話群組的成員必須處於 Teams 的部署模式。 如需 Teams 部署模式的詳細資料，請參閱[瞭解 Microsoft Teams 和商務用 Skype共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>需要授權

使用者必須獲指派Microsoft Teams 電話系統授權，才能設定並使用通話共用和群組通話接聽。 如需授權模型的其他詳細資料，請參閱 [電話系統提供以下](/MicrosoftTeams/here-s-what-you-get-with-phone-system)專案。

## <a name="configure-group-call-pickup"></a>設定群組通話取貨

若要設定群組通話接聽，使用者會先設定通話群組 (這與安全性群組或 Microsoft 365 群組) 不同，然後再新增想要共用通話的使用者。 然後，他們選擇同時撥打或來電轉接設定。 如需詳細資訊和逐步程式，請參閱 [Teams 中的來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

通話群組建立和通知喜好設定是使用者導向的功能;系統管理員不需要為使用者設定這些功能。 無法從安全性群組或 Microsoft 365 群組建立通話群組;它們必須在 Teams 中建立。

系統管理員應透過 **TeamsCallingPolicy AllowCallGroups** 設定為使用者啟用通話群組。 系統管理員也可以透過 Teams 管理員入口網站啟用這項功能。  此外，設定的使用者也可以直接透過用戶端設定他們的通話群組。 管理員或使用者無法互相封鎖設定，但 Teams 管理員入口網站和 Teams 用戶端應在兩個位置正確顯示此關聯。 

重要：當系統管理員在使用者 (開啟通話群組且已設定通話群組關聯) 後，系統管理員必須在 Teams 系統管理中心為使用者清除通話群組關聯，以避免錯誤的通話路由。 

## <a name="limitations"></a>限制

每個設定的通話群組最多可以有 25 個使用者或 32，768 個字元。 

## <a name="more-information"></a>詳細資訊

[Teams 中的來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
