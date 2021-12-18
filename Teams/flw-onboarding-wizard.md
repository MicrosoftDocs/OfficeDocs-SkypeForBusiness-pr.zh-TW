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
description: 瞭解如何使用前線員工上線精靈，在專為貴組織的前線員工Teams中快速部署體驗。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25508b3224ab7eab28157cbff268bb6b164686d5
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563650"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>使用前線員工上線精靈，讓前線員工上線並順利上線

## <a name="overview"></a>概觀

系統中的前線員工上線精靈Microsoft 365 系統管理中心簡化將前線員工上線到貴組織。 精靈可讓您在專為前線員工量Microsoft Teams快速部署體驗。 使用精靈，您可以輕鬆地開始為Teams前線員工進行試驗部署。

精靈會為前線員工設定團隊，並將授權和策略套件指派給每個[](manage-policy-packages.md)團隊成員。 您可以從頭開始建立小組，或從小組範本建立[](get-started-with-teams-templates-in-the-admin-console.md)小組，然後新增使用者並指派角色。 角色會決定精靈指派給每個使用者的政策套件。

目前，精靈支援每次執行時新增 100 個使用者。 我們正努力儘快增加每一次執行的使用者數目。 請返回這裡查看最新更新。

精靈可供至少擁有一個 F 授權的所有 [組織使用](https://www.microsoft.com/microsoft-365/enterprise/frontline)。 您可以執行精靈多次，因為您需要在組織Teams位置或網站將精靈推出給前線員工。

> [!NOTE]
> 此精靈可讓您快速上線員工，Teams完成Microsoft 365 系統管理中心。 若要瞭解如何使用腳本將Teams部署至前線員工，請參閱如何為前線員工Teams部署[資源。](flw-scripted-deployment.md)

> [!NOTE]
> 精靈目前不支援 [敏感度標籤](sensitivity-labels.md) 。 如果貴組織需要敏感度標籤來建立團隊，您就不會在 Microsoft 365 系統管理中心。

## <a name="run-the-wizard"></a>執行精靈

1. 在左側流覽的 [Microsoft 365 系統管理中心，選擇](https://admin.microsoft.com/)**設定**。 請前往應用程式 **與電子郵件** 區段，然後在讓前線員工上線並順利運作 **下，選取****** 在這裡，您可以深入瞭解前線Microsoft 365提供的功能。

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="螢幕擷取畫面顯示在 Microsoft 365 系統管理中心 中前線員工上線體驗的詳細資訊頁面Microsoft 365 系統管理中心" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. 當您準備好時，請選取 **開始** 執行精靈。

3. 輸入小組的名稱、新增一或多個團隊擁有者，然後選取隱私權設定。 接著，選擇是從頭開始建立小組，還是從小組範本建立團隊。 小組範本提供預先定義的頻道和定位停駐點，可針對特定業務需求或專案優化團隊。

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="精靈的設定小組頁面的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. 新增使用者至小組。 您也可以新增群組。 如果您新增群組，請記住，授權和策略套件會直接指派給群組中的每個使用者，而不是群組本身。

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="精靈中新增使用者頁面的螢幕擷取畫面，您可以在此新增使用者和群組至小組" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. 將下列其中一個角色指派給每個團隊成員：前線工作者、前線管理員、無。 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="精靈中指派角色、位置和授權給小組成員之精靈之工作角色頁面的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    指派前線工作者或前線管理員角色，該使用者會收到一個策略套件。 此政策套件會針對他們的角色Teams建立一個體驗。 此體驗包含預先釘選的 App 和適用于健康前線員工和主管通訊和共同合作的政策。

    接下來，選取一個位置，並指派一Microsoft 365 F 授權給每個團隊成員。 如果您沒有足夠的授權，您可以 **選取購買更多** 授權以購買更多授權。  

6. 選擇精靈完成之後收到狀態電子郵件的人。 電子郵件包含建立小組、新增小組成員，以及指派授權和策略套件給每個小組成員之精靈所執行之動作的成功與失敗 &mdash; 資訊。 使用這項資訊來疑難排解任何可能發生的錯誤。

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="精靈的新增狀態電子郵件收件者頁面的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. 請閱閱您的選取專案，然後 **選取確認**。

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="在精靈的檢查小組頁面螢幕擷取畫面中，您可以在這裡查看小組設定" lightbox="media/flw-onboarding-wizard-review-team.png":::

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
