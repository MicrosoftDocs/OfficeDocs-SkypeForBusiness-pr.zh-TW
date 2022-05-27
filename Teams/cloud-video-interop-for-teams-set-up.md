---
title: 設定適用于 Microsoft Teams 的雲端視訊 Interop
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
description: 本文說明如何為組織中的使用者規劃和設定雲端視訊 Interop。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b76e7c5e79b3928c7fb19ad9c5f5fb8f241b29a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674735"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>設定適用于 Microsoft Teams 的雲端視訊 Interop

選擇 [雲端視訊 Interop 合作夥伴 () ](cloud-video-interop.md)之後，您將需要規劃部署、使用布建詳細資料和合作夥伴租使用者金鑰進行設定，以及同意貴組織中的視訊外掛程式應用程式。 下圖概述程式。

![在貴組織中部署 CVI。](media/deploying-cvi.png)

## <a name="plan"></a>規劃

如需識別組織中要使用的合作夥伴或合作夥伴的相關資訊，請參閱雲端視訊[Interop](cloud-video-interop.md)以取得Microsoft Teams。

若要規劃使用者型/並行/全網站啟用：

- 挑選您使用的部署模型/託管模型
- 選取適合貴組織的授權方案。
- 規劃 VM 的容量是您要託管視訊的基礎結構。

## <a name="configure"></a>配置

若要設定雲端視訊 Interop，請遵循下列步驟。

1. 從您選擇 (租使用者金鑰、appIds...) 的合作夥伴/合作夥伴取得組態資訊。您可以使用組織中的一或多個視訊交互合作夥伴

2. 確定您的網路設定正確。 針對周邊網路周轉設定標準型視訊防火牆以獲得支援。 例如：
    - Cisco VCS-e
    - Polycom RPAD

3. 使用 Exchange 和 OTD 設定整合式會議室。 在大多數情況下，您必須在您的環境中設定和設定其他轉送。

## <a name="provision"></a>提供

租使用者金鑰會是撥出到合作夥伴服務。 在下列範例中，813878896@t.plcm.vc 是租使用者金鑰。

![租使用者金鑰範例。](media/tenant-key-example.png)

您將需要執行下列 Cmdlet 來布建租使用者金鑰，同時也可讓選取的使用者或整個組織建立具有視訊間座標的會議。

- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy)：** Microsoft 會為每個支援的合作夥伴提供預先建構的原則，可讓您指定要用於雲端視訊的合作夥伴 () 。

    此 Cmdlet 可讓您識別可在組織中使用的預先建構原則。 您可以利用Grant-CsTeamsVideoInteropServicePolicy Cmdlet，將此原則指派給一或多個使用者。

- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy)：** Grant-CsTeamsVideoInteropServicePolicy Cmdlet 可讓您指派預先建構的原則供組織使用，或將原則指派給特定使用者。

- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider)：** 使用New-CsVideoInteropServiceProvider指定貴組織想要使用之受支援的 CVI 合作夥伴的相關資訊。

- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider)：** 使用Set-CsVideoInteropServiceProvider更新貴組織所使用之受支援的 CVI 合作夥伴的相關資訊。

- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider)：** 取得已設定供組織內使用的所有提供者。

- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider)：** 使用 Remove-CsVideoInteropServiceProvider 移除貴組織不再使用之提供者的所有相關提供者資訊。

## <a name="consent"></a>同意

您必須提供視訊電話會議裝置 (VTC 的許可權同意，) 透過合作夥伴服務加入貴組織的會議。 您的合作夥伴也會提供此同意連結。

完成這些步驟後，透過上述 Grant Cmdlet 個別啟用的使用者，或如果已啟用租使用者，組織中的所有使用者都會在他們排程的所有Teams會議中具有 VTC 座標。 任何 VTC 都可以透過這些座標加入這些會議。

|名稱|應用程式許可權簡短描述| 描述|
|---|---|---|
|Calls.JoinGroupCall.All|以應用程式 (預覽) 加入群組通話和會議|可讓應用程式加入貴組織中的群組通話和排定的會議，而不需要登入的使用者。  應用程式會以目錄使用者的許可權加入租使用者中的會議。|
|Calls.JoinGroupCallasGuest.all|以來賓使用者身分加入群組通話和會議 (預覽) |可讓應用程式在貴組織中匿名加入群組通話和排定的會議，而不需要登入使用者。  應用程式會以來賓身分加入您租使用者中的會議。|
|Calls.AccessMedia.All|透過應用程式存取通話中的媒體串流， (預覽) |允許應用程式直接存取通話中的媒體串流，而不需要登入的使用者。|
|OnlineMeetings.Read.All| (預覽) 閱讀線上會議詳細資料|可讓應用程式在不使用登入使用者的情況下閱讀貴組織的線上會議詳細資料。|

## <a name="schedule"></a>附表

接下來，使用視訊交互座標安排Teams會議。 啟用的使用者可以透過下列方式排程團隊會議：

- [Teams Outlook 的會議增益集](teams-add-in-for-outlook.md)
- Teams用戶端桌面和行動裝置

## <a name="join"></a>加入

您可以使用 VTC 裝置以下列方式加入Teams會議：

- IVR (互動式語音回應) 
  - 您可以使用tenantkey@domain撥入合作夥伴的 IVR。
  - 一旦您進入合作夥伴 IVR，系統會提示您輸入 VTC 會議Id，然後將您連線至Teams會議。
- 直撥
  - 您可以直接撥入Teams會議，而不需使用完整的租使用者金鑰串直接撥號功能與合作夥伴的 IVR 互動。VTC ConferenceId@domain。
- 單點觸控轉盤
  - 如果您有整合式Teams室，您可以使用合作夥伴 (提供的單點觸控撥號功能，而不需要輸入任何撥號字串) 。

最後，使用音訊、視訊和內容共用功能，與Teams使用者一起參與會議。
