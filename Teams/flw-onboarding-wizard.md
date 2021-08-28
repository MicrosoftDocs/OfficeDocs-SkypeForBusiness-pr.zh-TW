---
title: 使用前線員工上線精靈，讓前線員工上線並順利上線
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 Frontline 員工上線精靈，在專為貴組織的前線員工Teams中快速部署體驗。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: da44a5eb25e56a974214472782e424cda735b6dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636801"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>使用前線員工上線精靈，讓前線員工上線並順利上線

> [!NOTE]
> 本文將說明尚未發行的功能。 即將推出。 如果您是系統管理員，您可以瞭解此功能何時會發行于郵件中心 (中[Microsoft 365 系統管理中心) 。](https://portal.office.com/adminportal/home) 若要隨時瞭解即將推出的Teams功能，請查看 Microsoft 365[藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

## <a name="overview"></a>概觀

Microsoft 365 系統管理中心中的前線員工上線精靈可簡化將前線員工加入貴組織。 精靈可讓您在專為前線員工量Microsoft Teams快速部署體驗。 使用精靈，您可以輕鬆地開始為組織的前線Teams進行試驗部署。

精靈會為前線員工設定團隊，並將授權和策略套件指派給每個[](manage-policy-packages.md)團隊成員。 您可以從頭開始建立小組，或從小組範本建立[](get-started-with-teams-templates-in-the-admin-console.md)小組，然後新增使用者並指派角色。 角色會決定精靈指派給每個使用者的政策套件。

精靈可供至少擁有一個 F 授權Microsoft 365使用。 您可以執行精靈多次，因為您需要將Teams到您組織不同位置或網站的前線員工。

> [!NOTE]
> 此精靈可讓您快速上線員工，Teams完成Microsoft 365 系統管理中心。 若要進一Teams腳本將人員部署至前線員工，請參閱如何Teams前線員工[部署資源](flw-scripted-deployment.md)。

## <a name="run-the-wizard"></a>執行精靈

1. 在左側流覽中 [，Microsoft 365 系統管理中心](https://admin.microsoft.com/)**設定**。 請前往應用程式 **與電子郵件** 區段，然後在讓前線員工上線並順利運作 **下，選取****** 在這裡，您可以深入瞭解前線Microsoft 365提供的功能。

2. 當您準備好時，請選取 **開始** 執行精靈。

3. 輸入小組的名稱、選取隱私權設定，以及新增一或多個團隊擁有者。 接著，選擇是從頭開始建立小組，還是從小組範本建立團隊。 小組範本提供預先定義的頻道和定位停駐點，可針對特定業務需求或專案優化團隊。

4. 新增使用者至小組。 您也可以新增群組。 如果您新增群組，請記住，授權和策略套件會直接指派給群組中的每個使用者，而不是群組本身。

5. 指派下列其中一個角色給每個團隊成員。

    - 前線工作人員
    - 前線管理員
    - 無

    指派前線員工或前線管理員角色，該使用者Teams角色量身打造的體驗。 這包括預先釘選的應用程式和適用于健康前線員工和主管通訊和共同合作的政策。

    接下來，為每個Microsoft 365指派 F 授權。 如果您沒有足夠的授權，您可以選取購買更多授權以購買更多授權。  

6. 選擇精靈完成之後收到狀態電子郵件的人。 電子郵件包含建立小組、新增小組成員，以及指派授權和策略套件給每個小組成員之精靈所執行之動作的成功與失敗 &mdash; 資訊。 使用這項資訊來疑難排解任何可能發生的錯誤。

7. 請閱閱您的選取專案，然後 **選取確認**。

    精靈會建立您的小組，並將授權和策略套件指派給小組成員。 這可能需要幾分鐘才能完成，之後您選取的收件者會收到狀態電子郵件。

8. 您上路了，但尚未完成！ 接下來，請查看執行本文 [精靈一節後](#what-to-do-after-running-the-wizard) 該做什麼。

## <a name="what-to-do-after-running-the-wizard"></a>執行精靈後該做什麼

執行精靈之後，必須：

- 請讓前線員工和主管知道他們已指派Teams授權。
- 如果您使用的是共用裝置，請確定Teams裝置上安裝該裝置。 如果貴組織使用「攜帶您自己的裝置」模型，請讓前線員工和主管知道他們必須下載並安裝Teams裝置。

第一次Teams前線員工開啟時，他們會收到量身打造的首次執行體驗，包括聊天和頻道、通話和任務管理，Teams。

## <a name="related-articles"></a>相關文章

- [在 Teams 中管理原則套件](manage-policy-packages.md)
- [在系統管理中心使用Teams範本](get-started-with-teams-templates-in-the-admin-console.md)