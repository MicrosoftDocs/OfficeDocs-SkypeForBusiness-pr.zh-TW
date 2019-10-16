---
title: 為 Microsoft 團隊設定雲端影片互通性
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: 本文說明如何規劃及設定貴組織使用者的雲端視頻互通性。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a94292719f8f93b818cbc52dd312859611940e3b
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516658"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>為 Microsoft 團隊設定雲端影片互通性

在您[選擇雲端視頻 Interop 合作夥伴](cloud-video-interop.md)之後，您將需要規劃您的部署、使用提供詳細資料與合作夥伴租使用者金鑰的設定，以及同意您組織中的視頻互通性應用程式。 下圖概述此程式。 

![在組織中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a>平面圖

請參閱[Microsoft 團隊的雲端影片交互操作](cloud-video-interop.md)，以取得有關如何識別貴組織中要使用的合作夥伴或合作夥伴的資訊。 

規劃使用者的基礎/並行/網站範圍啟用： 

- 挑選部署模型/託管模型供您使用
- 選取適用于貴組織的授權方案。 
- 針對 Vm 的容量進行規劃是您要裝載的是您的影片基礎結構。

## <a name="configure"></a>設定 

若要設定雲端視頻互通性，請遵循下列步驟。 

1. 從您所選的合作夥伴/合作夥伴取得配置資訊（租使用者金鑰、appIds ...）。 您可以在組織中使用一或多個視頻互通性合作夥伴 

2. 確定您的網路已正確設定。 針對您的周邊網路遍歷設定您的標準視頻防火牆以支援。 例如： 
    - Cisco VCS-e                  
    - Polycom RPAD

3. 使用 exchange 和 OTD 設定整合的會議室。 在大多數情況下，需要在您的環境中設定和設定額外的轉接。


## <a name="provision"></a>布建
 
租使用者金鑰就是向合作夥伴服務撥出。 在下列範例中，813878896@t.plcm.vc 是租使用者金鑰。 

![租使用者金鑰範例](media/tenant-key-example.png) 

您必須執行下列 Cmdlet 來設定租使用者金鑰，也可讓 [選取使用者] 或整個組織建立含影片交互操作座標的會議。

 
- ** [CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy)：** Microsoft 會針對我們支援的每個合作夥伴提供預先構造的原則，讓您指定要用於雲端影片互通性的合作夥伴。

    這個 Cmdlet 可讓您識別您可以在組織中使用的預先構造原則。 您可以利用 Grant CsTeamsVideoInteropServicePolicy Cmdlet，將此原則指派給一或多個使用者。
 
- **[授與 CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy)：** Grant CsTeamsVideoInteropServicePolicy Cmdlet 可讓您指派預先構造的原則供貴組織使用，或將原則指派給特定的使用者。
 
- **[新-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider)：** 使用新-CsVideoInteropServiceProvider 指定貴組織想要使用之受支援之 CVI 合作夥伴的相關資訊。
 
- ** [CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider)：** 使用 CsVideoInteropServiceProvider，更新貴組織使用之受支援之 CVI 夥伴的相關資訊。
 
- ** [CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider)：** 取得已設定為在組織內使用的所有提供者。
 
- **[移除-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider)：** 使用 [移除-CsVideoInteropServiceProvider]，移除貴組織不再使用之提供者的所有提供者資訊。  
 
## <a name="consent"></a>同意

您必須為影片 teleconferencing 裝置（VTCs）提供許可權，才能透過合作夥伴服務加入貴組織的會議。 您的合作夥伴也會提供此同意連結。  
 
完成這些步驟後，透過上述授權 Cmdlet 或組織中的所有使用者（如果已啟用租使用者），會在排程的所有團隊會議中擁有 VTC 座標。 任何 VTC 都可以透過這些座標加入這些會議。


|名稱|應用程式許可權簡短描述| 說明|
|--|--|---|
|JoinGroupCall。|以應用程式（預覽）加入群組通話與會議|允許 app 在您的組織中加入群組通話和排程會議，而無需登入的使用者。  App 將會以目錄使用者的許可權加入到您租使用者的會議中。|
|JoinGroupCallasGuest。|以來賓使用者身分加入群組通話和會議（預覽版）|允許 app 在沒有登入使用者的情況下，以匿名方式加入組織中的群組通話和排程會議。  App 會以來賓身分加入到您租使用者的會議中。|
|AccessMedia。|以應用程式（預覽）存取通話中的媒體資料流程|允許 app 直接存取通話中的媒體資料流程，無需登入的使用者。|
|OnlineMeetings. 全部閱讀. 全部|閱讀線上會議詳細資料（預覽版）|允許 app 在您的組織中讀取線上會議詳細資料，不需要登入的使用者。|

## <a name="schedule"></a>表

接下來，使用影片交互操作座標排程團隊會議。 已啟用的使用者可以透過以下方式排程團隊會議：
- [Outlook 的團隊會議增益集](teams-add-in-for-outlook.md)
- 團隊用戶端桌面及行動裝置


## <a name="join"></a>起來

您可以透過下列方式，與您的 VTC 裝置加入團隊會議：
 
- IVR （互動式語音回復）
    - 您可以使用 tenantkey @ 網域撥入合作夥伴的 IVR。 
    - 在您進入合作夥伴 IVR 之後，系統會提示您輸入 VTC conferenceId，這會將您連線至 [團隊會議]。
- 直接撥號
    - 您可以直接撥入小組會議，而不需與夥伴的 IVR 互動，只要使用 [直接撥號] 功能 tenantkey 的完整字串即可。VTC ConferenceId @ 網域。
- 單點觸控撥號
    - 如果您有整合的小組聊天室，您可以使用合作夥伴提供的單一觸控式撥號功能（不需要輸入任何撥號字串）。

最後，在會議中使用音訊、影片和內容共用與團隊使用者接洽。 
