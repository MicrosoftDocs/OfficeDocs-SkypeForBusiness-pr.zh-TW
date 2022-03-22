---
title: 在面板上簽入和Microsoft Teams釋放
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: 本文提供如何在面板裝置上啟用簽入Teams發行指南。
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689068"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>在面板上簽入和Microsoft Teams釋放

啟用簽入和會議室發行時，使用者會Teams會議開始時所保留會議室的面板。 如果使用者未在會議開始時間後的設定時間內簽入，會議室會拒絕會議邀請、傳送取消訊息給會議召集人，而會議室可供其他人保留。  

## <a name="requirements"></a>需求 

此功能可在獨立式面板部署Teams使用。 您也可以將 Teams 面板與 Android Teams 會議室 與 App 版本 1449/1.0.96.2022011305 或更新版本配對，以使用其他功能，例如簽入通知。  

## <a name="enable-check-in-and-room-release"></a>啟用簽入和會議室釋放 

根據預設，簽入和會議室發行會關閉。 若要開啟，  

1. 在 Teams面板上，使用系統管理員認證來登錄。  

2. 請前往 **設定 >裝置設定 >管理設定 >面板應用程式設定 >會議**。

3. 如果沒有人檢查，請開啟發行空間。

4. 若要調整使用者在會議室發行前必須簽入的時間量，請前往發行之後：然後從下拉式清單中選擇一個選項。  

當Teams面板與 Android Teams會議室配對時，使用者可以在會議室中簽入Teams會議。  

## <a name="turn-on-check-in-notifications"></a>開啟簽入通知

> [!NOTE]
> 此功能目前僅適用于與 Android Teams會議室配對的Teams面板。 Teams面板Teams聊天室必須簽到相同的資源帳戶。 如需[深入瞭解Teams，請參閱將 Microsoft Teams面板與 Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)上的會議室配對。  

當會議繼續超過保留的時段時，會送出簽入通知。 一旦下一個會議的使用者進入，通知會顯示在會議室顯示器的前方，位於其排定的會議開始時間，讓先前的會議參與者知道他們的預約已結束，而其他人正在等待空間。  

若要開啟簽入通知，  

1. 在 Teams面板上，使用系統管理員認證來登錄。 

2. 請前往 **設定 >裝置設定 >管理設定 >面板應用程式設定 >會議**。

3. 前往 **簽入並** 開啟傳送 **簽入通知**。

## <a name="related-topics"></a>相關主題

- [如何使用Microsoft Teams面板](use-teams-panels.md)

- [Microsoft Teams面板](teams-panels.md)