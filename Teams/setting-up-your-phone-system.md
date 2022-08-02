---
title: 設定貴組織的 [電話系統]
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: 有關如何在 Microsoft 365 中為貴組織設定 Teams Phone System 的逐步指南。
ms.openlocfilehash: 7f5a29bc5d57d59cf8d63dbe1f61db18a906e110
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156898"
---
# <a name="set-up-phone-system-in-your-organization"></a>設定貴組織的 [電話系統]

本文提供設定電話系統之內容的藍圖--Microsoft 在 Microsoft 365 雲端啟用通話控制和私人分支 Exchange (PBX) 功能的技術。 更多詳細資訊的連結可在每一個步驟的結尾處取得。

閱讀本文之前，請確定您已閱讀 [什麼是電話系統](what-is-phone-system-in-office-365.md) ， [以下是您透過電話系統取得的內容](here-s-what-you-get-with-phone-system.md)。 後兩篇文章說明電話系統需求和功能。

本文將說明下列步驟：

- [步驟 1：購買並指派電話系統授權](#step-1-buy-and-assign-a-phone-system-license)
- [步驟 2：選擇 PSTN 連線選項](#step-2-choose-a-pstn-connectivity-option)
- [步驟 3：取得使用者的電話號碼](#step-3-get-phone-numbers-for-your-users)
- [步驟 4：取得服務的電話號碼](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [步驟 5：如果您想要設定通話佇列](#step-5-if-you-want-to-set-up-a-call-queue)
- [步驟 6：如果您想要設定自動語音應答](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [步驟 7：設定免付費電話號碼的通訊點數](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>步驟 1：購買並指派電話系統授權

若要指派電話系統授權給單一使用者，步驟與指派 Microsoft 365 授權相同。 您也可以大量指派授權給多個使用者。 如需有關可用的電話系統授權，以及如何取得和指派授權的詳細資訊，請參閱 [Teams 附加元件授權](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) 和 [指派 Microsoft Teams 附加元件授權](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)。

## <a name="step-2-choose-a-pstn-connectivity-option"></a>步驟 2. 選擇 PSTN 連線選項

若要讓使用者撥打和接聽外部電話，您必須將電話系統連線到公用交換電話網路 (PSTN) 。 Microsoft 提供多種連線到 PSTN 的選項，包括：

- 通話方案。 將 Microsoft 做為 PSTN 電信業者的所有雲端解決方案。

- 運算子連線。 如果您現有的電信業者參與 Microsoft 運算子連線計畫，他們可以為您管理 PSTN 通話和會話框線控制器 (SBC) 。

- 直接路由。 將您的 SBC 連線至手機系統，以使用您自己的 PSTN 電信業者。

如需所有連線選項的詳細資訊，請參閱 [PSTN 連線選項](pstn-connectivity.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步驟 3：取得使用者的電話號碼

在您設定組織中的使用者撥打和接聽電話之前，您必須先為其取得電話號碼。

如需如何管理使用者電話號碼的相關資訊，請參閱下列文章。 您管理使用者號碼的方式取決於您選擇的 PSTN 連線選項。

- [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md) – 提供電話號碼類型的概觀，並提供取得及管理號碼的特定文章連結，視您的 PSTN 連線選項而定。
說明這兩種 [類型的使用者電話號碼](manage-phone-numbers-landing-page.md#user-telephone-numbers)。

- [指派、變更或移除使用者的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md) – 說明如何指派和管理您取得的電話號碼。

- [您可以取得多少電話號碼](how-many-phone-numbers-can-you-get.md) – 根據您購買和指派的電話號碼類型和授權類型，描述您可以取得多少電話號碼。

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>步驟 4：取得服務的電話號碼 (通話佇列、自動語音應答) 

除了取得使用者的電話號碼，您還可以取得自動語音應答和通話佇列等服務的付費或免付費電話號碼。 服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。

您可以從 Microsoft 取得您的授權所包含的服務號碼。 如果您透過運算子連線或直接路由擁有 PSTN 連線能力，您可以使用由您自己的電信業者或電信業者所提供的服務號碼。

如需詳細資訊，請參閱：

- [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md) – 提供電話號碼類型的概觀，並提供取得及管理號碼的特定文章連結，視您的 PSTN 連線選項而定。
說明您授權中包含的 Microsoft 提供的 [服務電話號碼](manage-phone-numbers-landing-page.md#service-telephone-numbers) 。 如需運算子連線或直接路由所提供的服務號碼的相關資訊，請連絡您的提供者。

- [您可以取得多少電話號碼](how-many-phone-numbers-can-you-get.md) – 根據您購買和指派的電話號碼類型和授權類型，描述您可以取得多少電話號碼。

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>步驟 5：如果您想要設定通話佇列

通話佇列包括當某人撥入貴組織的電話號碼時所使用的問候語、自動保留通話的功能，以及搜尋下一個可用來電代理程式處理通話的功能。 您可以為組織建立單一或多個通話佇列。

如需通話佇列的詳細資訊，請參閱 [建立通話佇列](create-a-phone-system-call-queue.md)。

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>步驟 6：如果您想要設定自動語音應答

自動語音應答可讓撥入貴組織的人員流覽功能表系統，讓他們前往正確的部門、通話佇列、人員或電信業者。

如需設定自動語音應答的相關資訊，請參閱 [設定自動語音應答](create-a-phone-system-auto-attendant.md)。

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>步驟 7：設定免付費電話號碼的通訊點數

如果您想要搭配 Microsoft Teams 使用免付費電話號碼，您必須設定通訊點數。 免付費電話每分鐘計費一次，且需要有正向的通訊點數餘額。

通訊點數是新增免付費電話號碼的便利方式，如下所示：

- 包含語音應用程式的服務號碼，例如自動語音應答或通話佇列。

- 若要撥打任何國際電話號碼，當您有國內通話方案訂閱，或超過國內和國際通話方案訂閱中包含的內容。

- 一旦您將每月的分鐘分配用盡後，若要撥出並每分鐘支付一次。

- 若要撥出並按分鐘支付所有撥出電話，如果您有隨選即用通話方案。

如需詳細資訊，請參閱 [什麼是通訊點數？](what-are-communications-credits.md) 以及 [為貴組織設定通訊點](set-up-communications-credits-for-your-organization.md)數。

## <a name="related-articles"></a>相關文章

- [什麼是電話系統](what-is-phone-system-in-office-365.md)

- [以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

- [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md)
