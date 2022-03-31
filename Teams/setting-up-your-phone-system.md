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
description: 逐步指南詳述如何在 Teams 電話系統中為貴組織設定Microsoft 365。
ms.openlocfilehash: 6b56c68e7316c78c7c1881d6e9d6ca39b13823b1
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556294"
---
# <a name="set-up-phone-system-in-your-organization"></a>設定貴組織的 [電話系統]

本文提供設定 電話系統 的內容藍圖，此為 Microsoft 在雲端中啟用通話控制與私人分支 Exchange (PBX) 功能Microsoft 365藍圖。 每個步驟的結尾都有更詳細的資訊連結。 

在閱讀本文之前，請確認您閱讀過電話系統[](what-is-phone-system-in-office-365.md)，以下是您取得[電話系統](here-s-what-you-get-with-phone-system.md)。 後兩篇文章說明電話系統需求與功能。    

本文將說明下列步驟： 

- [步驟 1：購買並指派電話系統授權](#step-1-buy-and-assign-a-phone-system-license)  
- [步驟 2：選擇 PSTN 連接選項](#step-2-choose-a-pstn-connectivity-option) 
- [步驟 3：取得使用者的電話號碼](#step-3-get-phone-numbers-for-your-users)
- [步驟 4：取得服務的電話號碼](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [步驟 5：如果您想要設定通話佇列](#step-5-if-you-want-to-set-up-a-call-queue) 
- [步驟 6：如果您想要設定自動話務員](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [步驟 7：設定免付費號碼的通訊信用額度](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>步驟 1：購買並指派電話系統授權

若要指派電話系統授權給單一使用者，步驟與指派授權Microsoft 365相同。 您也可以大量指派授權給多個使用者。 若要進一電話系統授權，以及如何取得和指派授權，請參閱 [Teams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing)附加元件授權和指派Microsoft Teams[附加元件授權](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)。

## <a name="step-2-choose-a-pstn-connectivity-option"></a>步驟 2. 選擇 PSTN 連接選項 
 
若要讓使用者撥打和接聽外部電話，您必須將電話電話系統到公用交換電話網絡 (PSTN) 。 Microsoft 提供多種連接至 PSTN 的選項，包括： 

- 通話方案。 以 Microsoft 做為 PSTN 電信公司的全雲端解決方案。 

- 電信業者連線。 如果您現有的電信公司參與 Microsoft 電信業者連線計畫，他們就可以管理 PSTN 通話和會話邊界控制 (SBC) SBC。 

- 直接路由。 使用您自己的 PSTN 電信公司，將 SBCs 連接到電話系統。 

有關所有連接選項的詳細資訊，請參閱 [PSTN 連接選項](pstn-connectivity.md)。   

## <a name="step-3-get-phone-numbers-for-your-users"></a>步驟 3：取得使用者的電話號碼

在您可以設定貴組織中使用者撥打和接聽電話之前，您必須先取得他們的電話號碼。

若要瞭解如何管理使用者的電話號碼，請參閱下列文章。 您管理使用者號碼的方式取決於您選擇的 PSTN 連接選項。   

- [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md) - 提供電話號碼類型概觀，並根據您的 PSTN 連接選項提供取得及管理號碼的特定文章連結。 說明兩種類型的 [使用者電話號碼](manage-phone-numbers-landing-page.md#user-telephone-numbers)。 
 
- [指派、變更或移除](assign-change-or-remove-a-phone-number-for-a-user.md) 使用者的電話號碼 - 說明如何指派和管理您取得的電話號碼。 
 
- [您可以取得多少](how-many-phone-numbers-can-you-get.md) 電話號碼 - 說明您可以取得的電話號碼數目，取決於您購買和指派的電話號碼類型及授權類型。 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>步驟 4：取得服務的電話號碼 (通話佇列、自動) 

除了取得使用者的電話號碼之外，您還可以取得自動電話機和通話佇列等服務的付費或免付費電話號碼。 服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。   

您可以向 Microsoft 取得授權中包含的服務號碼。 如果您使用 PSTN 電信業者連線或直接路由，您可以使用自己的電信公司或電信公司所提供的服務號碼。 

詳細資訊，請參閱：

- [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md) - 提供電話號碼類型概觀，並根據您的 PSTN 連接選項提供取得及管理號碼的特定文章連結。  
說明 [授權](manage-phone-numbers-landing-page.md#service-telephone-numbers) 中包含的 Microsoft 服務電話號碼。 如需由 電信業者連線或直接路由所提供的服務號碼相關資訊，請與您的提供者聯繫。 

- [您可以取得多少](how-many-phone-numbers-can-you-get.md) 電話號碼 - 說明您可以取得的電話號碼數目，取決於您購買和指派的電話號碼類型及授權類型。 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>步驟 5：如果您想要設定通話佇列

通話佇列包括當某人來電到貴組織的電話號碼時所使用的問候語、自動保留通話的能力，以及搜尋下一個可用的通話代理程式來處理通話的能力。 您可以為貴組織建立單一或多個通話佇列。 

有關通話佇列的資訊，請參閱 [建立通話佇列](create-a-phone-system-call-queue.md)。

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>步驟 6：如果您想要設定自動話務員

自動話務員可允許來電到貴組織的人流覽功能表系統，讓他們到正確的部門、通話佇列、人員或接線生。  

有關設定自動話務員的資訊，請參閱 [設定自動話務員](create-a-phone-system-auto-attendant.md)。

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>步驟 7：設定免付費號碼的通訊信用額度

如果您想要將免付費號碼與 Microsoft Teams一起使用，您必須設定通訊信用額度。 免付費通話費用為每分鐘計費，且需要正的通訊信用額度餘額。 

通訊信用額度是新增免付費號碼的便利方式，如下所示： 

- 使用語音應用程式的服務號碼，例如自動語音留言或通話佇列。 

- 當您擁有國內通話方案訂閱或國內及國際通話方案訂閱以外的號碼時，撥打任何國際電話號碼。 

- 當您用盡每月的分鐘分配後，撥出並按分鐘付款。 

詳細資訊請參閱 [通訊信用額度是什麼？](what-are-communications-credits.md) 以及為貴組織設定 [通訊信用額度](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>相關主題

- [什麼是電話系統](what-is-phone-system-in-office-365.md)

- [以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

- [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md)


    
  
 
