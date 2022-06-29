---
title: 使用前線工作者上線精靈，讓前線員工能夠順利上線
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用第一線工作人員入門精靈，在 Teams 中快速部署專為組織中的第一線員工和主管量身打造的體驗。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 160a8347e0ea79198f337fce460ced90f5de2931
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494510"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>使用前線工作者上線精靈，讓前線員工能夠順利上線

## <a name="overview"></a>概觀

Microsoft 365 系統管理中心中的 [第一線工作人員上線] 精靈簡化了將第一線工作人員上線到貴組織。 精靈可讓您在 Microsoft Teams 中快速部署專為前線員工量身打造的體驗。 您可以使用精靈，輕鬆地為組織中的一線工作人員開始進行 Teams 試驗部署。

精靈會為您的第一線員工設定一個團隊，並將授權和 [原則套件](manage-policy-packages.md) 指派給每個小組成員。 您可以從頭開始或從 [團隊範本建立團隊](get-started-with-teams-templates-in-the-admin-console.md)，然後新增使用者並指派角色。 角色會決定精靈指派給每個使用者的原則套件。

目前精靈支援在每次執行時新增 100 個使用者。 我們正在努力增加每次執行的使用者數目。 請返回此處查看最新的更新。

精靈可供擁有至少一個 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline)的所有組織使用。 您可以根據在組織中不同位置或網站上的前線員工推行 Teams 所需的次數，執行精靈的次數不限。

請觀看這段短片，概略瞭解如何執行精靈，讓您的第一線員工上線。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> 精靈尚未支援 [敏感度標籤](sensitivity-labels.md) 。 如果貴組織需要敏感度標籤才能建立團隊，您就不會在Microsoft 365 系統管理中心中看到精靈。

## <a name="run-the-wizard"></a>執行精靈

1. 在Microsoft 365 系統管理中心左側導 [覽](https://admin.microsoft.com/)中，選擇 **[設定]**。 移至 [ **應用程式與電子郵件** ] 區段，然後在 [ **讓您的第一線員工快速上手並執行**] 下，選取 [ **檢視]**。 您可以在這裡深入瞭解Microsoft 365 for frontline workers提供的功能。

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Microsoft 365 系統管理中心中第一線工作人員登入體驗詳細資料頁面的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. 當您準備好時，選取 **[開始** 執行精靈]。

3. 輸入團隊名稱、新增一或多個團隊擁有者，然後選取隱私權設定。 然後，選擇要從頭開始建立團隊，還是從團隊範本建立團隊。 團隊範本隨附預先定義的頻道和索引標籤，可針對特定商務需求或專案優化團隊。

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="精靈 [設定團隊] 頁面的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. 將使用者新增至團隊。 您也可以新增群組。 如果您新增群組，請記住，授權和原則套件是直接指派給群組中的每個使用者，而不是群組本身。

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="在精靈的 [新增使用者] 頁面中，將使用者和群組新增至小組的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. 將下列其中一個角色指派給每個小組成員：第一線工作人員、前線管理員、無。 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="精靈 [指派工作角色] 頁面的螢幕擷取畫面，您可以在其中指派角色、位置和授權給小組成員" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    藉由指派第一線工作人員或一線管理員角色，該使用者將會收到原則套件。 原則套件會在 Teams 中建立專為其角色量身打造的體驗。 此體驗包含預先釘選的應用程式和原則，適用于健康的第一線員工以及主管通訊和共同作業。

    接下來，選取一個位置，並將 Microsoft 365 F 授權指派給每個小組成員。 如果您沒有足夠的授權，您可以選取 **[購買更多授權** ] 以購買更多授權。  

6. 選擇精靈完成後收到狀態電子郵件的人員。 電子郵件包含由精靈 &mdash; 建立團隊、新增小組成員，以及指派授權和原則套件給每個小組成員所執行動作的成功與失敗資訊。 使用此資訊可針對可能發生的任何錯誤進行疑難排解。

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="精靈 [新增狀態電子郵件收件者] 頁面的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. 檢閱您的選取專案，然後選取 **[確認]**。

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="您在其中檢閱團隊設定的精靈 [檢閱小組] 頁面的螢幕擷取畫面" lightbox="media/flw-onboarding-wizard-review-team.png":::

    精靈會建立您的團隊，並將授權和原則套件指派給小組成員。 可能需要幾分鐘的時間才能完成，之後您選擇的收件者會收到一封狀態電子郵件。

8. 您已在途中，但尚未完成！ Next, check out the [What to do after running the wizard](#what-to-do-after-running-the-wizard) section of this article.

## <a name="what-to-do-after-running-the-wizard"></a>執行精靈之後的處理方式

執行精靈之後，請務必：

- 讓您的第一線工作人員和經理知道他們已獲指派 Teams 授權。
- 如果您的組織使用共用裝置，請確定這些裝置上已安裝 Teams。 您新增至團隊的使用者會收到歡迎電子郵件，提示他們開啟 Teams。
- 如果您的組織使用「攜帶您自己的裝置」 (BYOD) 模型，請讓您新增至團隊的每個使用者知道他們必須下載並安裝 Teams 到他們的裝置。 他們也會收到一封歡迎電子郵件，提示他們下載 Teams。

    > [!NOTE]
    > 請記住，擁有 F1 授權的使用者不會收到歡迎電子郵件，因為 F1 授權不含電子郵件存取權。  

當第一線員工第一次開啟 Teams 時，他們會獲得量身打造的初次執行體驗，包括聊天和頻道、通話，以及在 Teams 內的工作管理。

## <a name="related-articles"></a>相關文章

- [在 Teams 中管理原則套件](manage-policy-packages.md)
- [在 Teams 系統管理中心使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)
