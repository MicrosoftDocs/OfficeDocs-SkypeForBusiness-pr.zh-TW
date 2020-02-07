---
title: 設定組織的電話系統
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '瞭解如何為您的組織設定電話系統（雲端 PBX）。 '
ms.openlocfilehash: 71e12447d0a6951ef787bf7c7cd82024375e11fd
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837983"
---
# <a name="set-up-phone-system-in-your-organization"></a>在組織中設定電話系統

以下是在 Office 365 中設定電話系統的逐步指南。 在每個步驟的結尾，都提供其他詳細資訊的連結。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>步驟1：確認您的國家或地區有可用的電話系統

1.  首先，請移至[適用于音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)，然後從頁面頂端的清單中選取您的國家或地區。 
2.  在 [**電話系統**] 下，查看功能清單及詳細資料。 
3.  如果有可用的電話系統，請移至步驟2。 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>步驟2：購買並指派電話系統和通話方案授權

若要將電話系統和通話方案授權指派給單一使用者，這些步驟與指派 Office 365 授權是一樣的。  您也可以大量指派授權給多位使用者。 如需詳細資訊，請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。

如果通話方案不適用於您的國家或地區，請考慮使用直接路由將您的內部部署電話結構連線至 [電話系統]。  如需詳細資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步驟3：為您的使用者取得電話號碼

您必須先取得電話號碼，才能將貴組織中的使用者設定為撥打及接聽電話。

您有三種方式可取得使用者的號碼：
- 使用小組系統管理中心取得新數位。
- 取得小組系統管理中心無法使用的新號碼。
- 將現有的號碼從目前的服務提供者或電話轉接到 Office 365。

您必須使用 [**新增號碼**] 頁面來查看、搜尋、取得及保留這些號碼。 您可以依 [國家/地區]、[省/市] 及 [城市] 進行搜尋，然後輸入使用者所需的電話號碼數量。

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>使用團隊系統管理中心取得新使用者的電話號碼

1. 使用您的公司或學校帳戶登入 Microsoft 365。

2. 移至 [**團隊系統管理中心**]。
    
3. 在左導覽中，前往 [**語音** > **電話號碼**]，按一下 [**新增**]，然後依照提示進行。
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>取得團隊系統管理中心無法使用的新號碼
  
有時候（視您的國家/地區而定），您將無法使用小組系統管理中心來取得新號碼。 在這種情況下，您必須下載表單並將它傳送給我們。 若要瞭解如何要求新的使用者編號，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>從服務提供者或電話載波傳送埠或轉移電話號碼
  
- 如果您需要999或更少的使用者電話號碼，您可以使用 [小組系統管理中心] 中的 [**新的當地號碼埠順序**] 嚮導。 遵循將[電話號碼轉接給小組](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)，以轉接您的電話號碼中找到的步驟。
    
- 如果您需要端口超過999的電話號碼，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交埠訂單服務要求或訂單。 

如需取得新電話號碼或轉移現有號碼的詳細資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步驟4：取得服務電話號碼（音訊會議、通話佇列、自動語音應答）

除了從 Office 365 取得使用者的電話號碼之外，您還可以在 [音訊會議] （適用于 [會議室]）、[自動語音應答] 和 [通話佇列] 等服務中搜尋及取得付費或免付費電話號碼。 服務電話號碼的並行通話容量比使用者或訂閱者電話號碼要高。 例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>使用團隊系統管理中心取得新的服務號碼


1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [**團隊系統管理中心**]。

3. 在左側流覽窗格中，移至 [**語音** > **電話號碼** > ]，**新增號碼**，然後按一下 [**新的服務號碼**]。

    > [!IMPORTANT]
    > 若要在 [團隊管理中心] 的左導覽窗格中看到 [**語音**] 選項，您必須先購買至少一個**企業版 E5 授權**、一個**電話系統**附加元件授權或一個**音訊會議**附加元件授權。

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>取得團隊系統管理中心無法使用的新號碼
  
有時候（視您的國家/地區而定），您將無法使用小組系統管理中心來取得新號碼。 在這種情況下，您將需要下載表單並將它傳送給我們。 若要瞭解如何要求新號碼，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 

### <a name="port-or-transfer-existing-service-numbers"></a>移植或轉移現有的服務號碼

如果您想要從目前的服務提供者或承運人傳送服務號碼，您必須手動將埠訂單提交給 Microsoft。 您必須針對每一種類型的服務號碼（[收費電話]）提交不同的埠順序（免付費電話），您將會使用一份授權函式（LOA）傳送。 在授權信件（LOA）中，您必須選取正確的服務號碼類型。 當您聯繫 Microsoft 支援時，請指定您要轉移服務號碼（*而非使用者或訂閱者號碼*），或同時進行通話容量可能不足以處理呼叫量。 如果您想要使用電話號碼傳送電話號碼或進行其他動作，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>步驟5：如果您要設定通話方案

如果您已按照上述步驟進行，就表示您已購買並指派電話系統和授權，以及通話方案（步驟2），以及為使用者取得的電話號碼（步驟3），因此您的通話方案已部分設定。 若要完成設定通話方案的程式，請參閱[設定通話方案](set-up-calling-plans.md)。


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>步驟6：如果您想要設定音訊會議

有時候貴組織中的人員必須使用電話撥入會議。 Microsoft 團隊包括音訊會議功能，只適用于這種情況。 使用者可以使用電話撥入團隊會議，而不是在行動裝置或電腦上使用 [小組] 應用程式。
如需如何設定音訊會議的詳細資訊，請參閱[設定適用于小組的音訊會議](set-up-audio-conferencing-in-teams.md)。

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>步驟7：如果您想要設定雲端通話佇列

雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能，以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。 您可以為組織建立單一或多個通話佇列。

如需通話佇列的詳細資訊，請參閱[建立雲端通話佇列](create-a-phone-system-call-queue.md)。

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>步驟8：如果您想要設定雲端自動助理

自動語音應答讓撥入您組織的人員，並流覽功能表系統，以取得正確的部門、呼叫佇列、人員或接線員。 您可以使用商務用 Skype 系統管理中心，為您的組織建立自動語音應答。

如需設定雲端自動 attendendant 的相關資訊，請參閱[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答。


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步驟9：指派服務電話號碼（音訊會議、通話佇列、自動語音應答）

從**上述步驟 4**獲得您的服務號碼之後，您必須將他們指派給您想要的每一種類型的服務。 例如，如果您需要專用的服務電話號碼（付費或免費付費），您必須將號碼指派給會議橋。

- 對於音訊會議，您可以移至 [**團隊管理中心** > **會議** > ]**橋**，然後依照提示，將專用號碼指派給會議橋。  如需詳細資訊，請參閱[在音訊會議橋中變更付費或免付費電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

- 針對自動語音應答，您可以移至 [**小組系統管理中心** > **語音** > **自動**語音應答]，將專用號碼指派給自動語音應答，然後依照提示進行。  如需詳細資訊，請參閱[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答。

- 如果是通話佇列，您可以移至 [**小組系統管理中心** > **語音** > **通話] 佇列**，將專用號碼指派給呼叫佇列，然後依照提示進行。 如需詳細資訊，請參閱[建立雲端通話佇列](create-a-phone-system-call-queue.md)。

如需取得新服務號碼和移植現有服務號碼的詳細資訊，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)。

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>步驟10：為您的組織設定通訊點數

如果您想要將免付費電話號碼與 Microsoft 團隊搭配使用，您必須設定通訊點數。 Microsoft 建議您針對通話方案（國內或國際）及需要撥出至任何目的地的音訊會議使用者設定通訊點數。 包含許多國家/地區，但某些目的地可能不會包含在您的通話方案或音訊會議訂閱中。 

如果您沒有設定通訊信用帳單，並將**通訊點數**授權指派給您的使用者，而您的組織時間卻超出了幾分鐘（視您所在國家/地區的通話方案或音訊會議方案而定），這些使用者將無法撥打電話或撥出音訊會議會議。 如需詳細資訊（包括建議的融資金額），請參閱[什麼是通訊信用？](what-are-communications-credits.md) ，並[為您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>相關主題
[以下是您在 Office 365 中使用電話系統所取得的結果](here-s-what-you-get-with-phone-system.md)

[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
