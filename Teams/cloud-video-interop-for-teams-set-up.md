---
title: 設定雲端視Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: 本文說明如何為貴組織的使用者規劃及設定雲端視像交互操作。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe0ac66b8d1ff9afe43d4d57783e803f426c23c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732952"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>設定雲端視Microsoft Teams

選擇您的雲端視像交互操作合作夥伴 [ (](cloud-video-interop.md)) 之後，您必須規劃部署、設定與部署詳細資料及合作夥伴租使用者金鑰，以及同意貴組織的視像交互操作應用程式。 下圖概述程式。 

![在貴組織中部署 CVI。](media/deploying-cvi.png)

## <a name="plan"></a>規劃

請參閱[雲端視Microsoft Teams](cloud-video-interop.md)交互操作，以尋找識別合作夥伴或合作夥伴以在貴組織中使用的資訊。 

若要規劃使用者型/並行/全網站啟用： 

- 挑選適合您使用的部署模型/託管模型
- 選取適用于貴組織之授權計畫。 
- 規劃虛擬機器的容量是託管視像基礎結構。

## <a name="configure"></a>配置 

若要設定雲端視像交互操作，請遵循下列步驟。 

1. 從您選擇的合作夥伴/合作夥伴取得 (金鑰、appId...) 。 您可以在貴組織中使用一或多個視像交互操作合作夥伴 

2. 請確保您的網路已正確配置。 設定標準型視像防火牆，讓周邊網路進行橫向移動以提供支援。 例如： 
    - Cisco VCS-e                  
    - Polycom RPAD

3. 使用 Exchange 和 OTD 設定整合的會議室。 在大多數情況下，您的環境中需要設定和設定其他轉場。


## <a name="provision"></a>提供
 
租使用者金鑰會撥入合作夥伴服務。 在下列範例中，813878896@t.plcm.vc 是租使用者金鑰。 

![租使用者金鑰範例。](media/tenant-key-example.png) 

您必須執行下列 Cmdlet 來配置租使用者金鑰，同時啟用選取的使用者或整個組織，以視像交互操作座標建立會議。

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy)：** Microsoft 會針對每個支援的合作夥伴提供預先建構的策略，讓您指定 () 雲端視像交互操作。

    此 Cmdlet 可讓您識別可在貴組織中使用的預先建構策略。 您可以使用 Cmdlet，將這個Grant-CsTeamsVideoInteropServicePolicy指派給一或Grant-CsTeamsVideoInteropServicePolicy使用者。
 
- **[Grant-CsTeamsVideoInteropServicePolicy：](/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** Cmdlet Grant-CsTeamsVideoInteropServicePolicy Cmdlet 可讓您指派預先建構的策略，供貴組織使用，或將策略指派給特定使用者。
 
- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider)：** 使用 New-CsVideoInteropServiceProvider指定貴組織想使用之支援的 CVI 合作夥伴相關資訊。
 
- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider)：** 使用 Set-CsVideoInteropServiceProvider更新貴組織使用之支援 CVI 合作夥伴的資訊。
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider)：** 取得組織中所有已針對使用所配置的提供者。
 
- **[Remove-CsVideoInteropServiceProvider：](/powershell/module/skype/remove-csvideointeropserviceprovider)** 使用 Remove-CsVideoInteropServiceProvider移除貴組織不再使用之提供者的所有提供者資訊。  
 
## <a name="consent"></a>同意

您必須提供視距電話會議裝置的許可權同意， (RVC) 合作夥伴服務加入組織會議。 您的合作夥伴也會提供此同意連結。  
 
完成這些步驟後，透過上述 Grant Cmdlet 個別啟用的使用者，或啟用租使用者時組織中所有使用者，都會在排程的所有 Teams 會議中擁有 VTC 座標。 任何 VTC 都可以透過這些座標加入這些會議。


|名稱|應用程式許可權簡短描述| 描述|
|--|--|---|
|通話.JoinGroupCall.All|以應用程式加入群組通話和會議 (預覽) |允許應用程式加入貴組織的群組通話和排程會議，而不需要已登錄使用者。  應用程式會以目錄使用者的許可權加入租使用者中的會議。|
|通話.JoinGroupCallasGuest.All|以來賓使用者加入群組通話和會議 (預覽) |允許應用程式以匿名方式加入貴組織的群組通話和排程會議，而不需要已登錄使用者。  應用程式會以來賓的來賓加入租使用者中的會議。|
|通話.AccessMedia.All|以 App 在通話中存取媒體流， (預覽) |允許 App 直接存取通話中的媒體流，而不需要已登錄使用者。|
|OnlineMeetings.Read.All|閱讀線上會議詳細資料 (預覽) |允許應用程式讀取貴組織的線上會議詳細資料，而不需要已登錄使用者。|

## <a name="schedule"></a>附表

接下來，使用視Teams座標排程會議。 啟用的使用者可以透過以下方式排程團隊會議：
- [Teams會議Outlook](teams-add-in-for-outlook.md)
- Teams桌面和行動版


## <a name="join"></a>加入

您可以使用 VTC Teams，以下列方式加入會議：
 
- IVR (互動式語音回應) 
    - 您可以使用電話號碼撥入合作夥伴的 IVR tenantkey@domain。 
    - 當您在合作夥伴 IVR 中時，系統會提示您輸入 VTC meetingId，然後將您Teams會議。
- 直撥
    - 您可以直接撥入Teams，而不使用使用完整字串租使用者金鑰的直接撥號功能與合作夥伴的 IVR 互動。VTC ConferenceId@domain。
- 單鍵撥號
    - 如果您有整合式Teams，您可以使用合作夥伴提供的單鍵撥號功能 (不需要輸入任何撥號字串) 。

最後，使用Teams、視像和內容共用，與會議中的使用者互動。