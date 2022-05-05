---
title: Microsoft Teams面板上的簽入和會議室發行
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
description: 本文提供如何啟用面板裝置Teams簽入和會議室版本的指導方針。
ms.openlocfilehash: 3cf1f48a71f88f012c6d33ba608ee40b53cda474
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2022
ms.locfileid: "65218017"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Microsoft Teams面板上的簽入和會議室發行

啟用簽到並釋出會議室時，使用者會在會議開始時所保留的會議室中存回Teams面板。 如果使用者在會議開始時間之後的一定時間內沒有存回，會議室會拒絕會議邀請、傳送取消訊息給會議召集人，而其他人可以預約會議室。  

## <a name="requirements"></a>需求 

此功能可用於獨立Teams 面板部署。 您也可以將Teams面板與 Android 上的Teams 會議室搭配應用程式版本 1449/1.0.96.2022011305 或更新版本，以取得其他功能，例如簽入通知。  

## <a name="enable-check-in-and-room-release"></a>啟用簽入和會議室發行 

簽入和會議室版本預設為關閉。 若要將它開啟，  

1. 在Teams 面板上，使用您的系統管理員認證登入。  

2. 移至 **設定 > 裝置設定>系統管理設定> Teams系統管理設定>會議。**

3. 如果沒有人登入，請開啟發行室。

4. 若要調整使用者在會議室發行前必須存回的時間，請移至 [在下列 **之後發行]** ，然後從下拉式清單中選取選項。  

當Teams面板與 Android 上的Teams會議室配對時，使用者可以在Teams會議室上簽入會議。  

## <a name="turn-on-check-in-notifications"></a>開啟簽入通知

> [!NOTE]
> 此功能目前僅適用于與 Android 上Teams會議室配對的Teams面板。 Teams 面板和Teams必須登入相同的資源帳戶。 若要深入瞭解，請參閱[將Teams 面板與 Android 上的Microsoft Teams室配對](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)。  

當會議持續超過保留的時段時，就會傳送簽入通知。 一旦使用者從下一個會議進入會議後，通知就會出現在會議室的前方顯示器上，並顯示在其排定的會議開始時間，讓上一個會議參與者知道他們的預約已結束，而其他人正在等待空間。  

若要開啟簽入通知，  

1. 在Teams 面板上，使用您的系統管理員認證登入。 

2. 移至 **設定 > 裝置設定>系統管理設定> Teams系統管理設定>會議。**

3. 移至 **[簽** 到] 並開啟 [ **傳送簽入通知]**。

## <a name="related-topics"></a>相關主題

- [如何使用Microsoft Teams面板](use-teams-panels.md)

- [Microsoft Teams面板](teams-panels.md)
