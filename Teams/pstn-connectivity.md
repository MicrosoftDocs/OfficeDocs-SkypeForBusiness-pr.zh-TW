---
title: PSTN 連接選項
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 深入瞭解如何Teams PSTN (PSTN) 選項，以及您將為貴組織做出的決策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92b588de0041ab6cc1b74734f9a56b1e97f55166
ms.sourcegitcommit: 6aecab65836feaa8da14aad17a3088a18ece3bdf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2021
ms.locfileid: "61267826"
---
# <a name="pstn-connectivity-options"></a>PSTN 連接選項

Microsoft 透過您的Exchange (提供完整的私人分支) PBX 功能Teams 電話。 不過，若要讓使用者在組織外撥打電話，您必須將電話Teams 電話到公用交換電話網絡 (PSTN) 。

本文著重于 PSTN 連接選項。 有關 Microsoft 語音解決方案的詳細資訊，請參閱規劃您的Teams 電話[Teams](cloud-voice-landing-page.md)語音解決方案。

若要將Teams 電話 PSTN，您可以從下列選項中選擇：

- [**通話方案**](#teams-phone-with-calling-plan)。 以 Microsoft 做為 PSTN 電信公司的全雲端解決方案。

- [**運算子連線**](#teams-phone-with-operator-connect)，目前僅適用于公用 **預覽。**  使用運算子連線，如果您現有的電信公司是 Microsoft Operator 連線 計畫的參與者，他們可以管理 PSTN 通話和會話邊界控制器 (SBC) 。 

- [**直接路由**](#teams-phone-with-direct-routing)，可讓您將會話邊界控制器 (SBC)  (，) PSTN Teams 電話。


您也可以選擇選項群組合，這可讓您設計複雜環境的解決方案，或管理多步驟移移。

請注意，您選擇的選項會影響某些Teams 電話功能的配置方式。 詳細資訊，請參閱 [本文稍後的](#configuration-considerations) 組組考慮。


## <a name="teams-phone-with-calling-plan"></a>Teams 電話通話方案 

Teams 電話通話方案是 Microsoft 針對使用者所使用之全雲端語音Teams解決方案。 這是連接 PSTN Teams 電話最簡單的選項。 使用這個選項，Microsoft 會做為 PSTN 電信者，如下圖所示：

![圖表 1 顯示電話系統通話方案。](media/voice-solutions-simple.png)

如果您對下列專案回答是，Teams 電話通話方案是適合的解決方案：

- 通話方案可在您的地區使用。
- 您不需要保留目前的 PSTN 電信公司。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

使用此選項： 

- 您可以Teams 電話國內或國際通話方案，根據授權服務等級 (撥打世界各地的電話) 。

- 您不需要部署或維護內部部署，因為通話方案無法 &mdash; Microsoft 365。

- 注意：如有需要，您可以選擇透過直接路由連接支援的會話邊界控制器 (SBC) ，以與 SBC 支援的協力廠商 PBX、類比裝置及其他協力廠商電話設備進行互通性。

此選項需要不間斷地連接到Microsoft 365。

有關通話方案的資訊，請參閱下列文章：

- [哪一個通話方案適合您？](calling-plan-landing-page.md)
- [如何購買通話方案](calling-plans-for-office-365.md)
- [通話方案的適用國家與地區](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [設定通話方案](set-up-calling-plans.md)


## <a name="teams-phone-with-operator-connect"></a>Teams 電話運算子連線

如果您的現有電信連線是 Microsoft Operator 連線 計畫的參與者，他們就可以管理將 PSTN 通話帶到 Teams。 您的電信業者會管理 PSTN 通話服務和會話邊界 (SBC) ，讓您節省硬體購買和管理。

如果連線運算子或運算子，可能是適用于貴組織的解決方案：

- 您的地理位置無法提供 Microsoft 通話方案。
- 您偏好的電信公司是 Microsoft Operator 連線參與者。
- 您想要尋找新的電信公司，以在 Teams。

有關 Operator 連線 權益和需求的資訊，以及參與此計畫的電信公司清單，請參閱規劃運算子[連線。](operator-connect-plan.md) 若要瞭解如何設定運算子連線，請參閱[設定運算子連線。](operator-connect-configure.md)


## <a name="teams-phone-with-direct-routing"></a>Teams 電話直接路由

這個選項會Teams 電話直接路由，將電話網路連接到您的電話網絡，如下圖所示： 

![圖表 5 顯示電話系統路由的圖表。](media/voice-solution-with-direct-routing.png)

如果您對下列問題回答是，Teams 電話直接路由是適合的解決方案：

- 您想要在 Teams 中Teams 電話。
- 您需要保留目前的 PSTN 電信公司。
- 您想要混合路由，有些通話會透過通話方案進行，有些則透過您的電信公司進行。
- 您需要與協力廠商 PBX 和/或設備進行交互操作，例如架空傳呼機、類比裝置等。

使用此選項：

- 您可以在 SBC 中 (會話邊界控制器) Teams 電話，而不需要其他內部部署軟體。

- 您幾乎可以在任何電話電信業者Teams 電話。

- 您可以選擇設定及管理這個選項，也可以由您的電信公司或合作夥伴設定及管理 (詢問您的電信公司或合作夥伴是否提供此選項) 。

- 您可以設定電話設備之間的互通性，例如協力廠商 PBX 和類比裝置 &mdash; &mdash; Teams 電話。

此選項需要下列專案：

- 不間斷地Microsoft 365。

- 部署及維護支援的 SBC。

- 與協力廠商電信公司簽訂合約。
   (除非已部署為選項，為使用通話方案的使用者提供協力廠商 PBX、類比裝置或其他電話Teams 電話裝置) 

有關直接路由的資訊，請參閱下列文章：

- [規劃直接路由](direct-routing-plan.md)
- [設定直接路由](direct-routing-configure.md)
- [管理語音路由策略，以用於直接路由](manage-voice-routing-policies.md)
- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [通過直接路由認證的工作階段邊界控制器清單](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>組組考慮

無論您Teams 電話 PSTN 連接選項，大部分的功能都是相同的。 例如，通話未回音和轉接設定、來電轉接、保留的自訂音樂、通話保留、共用線路和語音應用程式都可供使用。 有關功能的完整清單Teams 電話，請參閱以下是您取得[的功能](here-s-what-you-get-with-phone-system.md)Teams 電話。

不過，功能有一些差異會影響您設定特定功能Teams 電話方式。 例如，直接路由需要額外的步驟來設定通話路由。 另一個範例是，直接路由提供位置式路由 (LBR) ，這樣您才能限制特定地理位置不允許的付費旁路。 

下表會強調主要組組差異。 表格後各節提供詳細資訊和詳細資料的連結。

| 選項 | 描述 | 電話號碼管理 | 通話路由 | 緊急通話可用性 |
| :------------| :-------| :-------| :-------| :-------| 
| 通話方案 | -Microsoft 會做為 PSTN 電信公司。<br>-不需要購買或管理 SBC。| 透過 Microsoft 取得。| -由 Microsoft 管理。 <br> -系統管理員設定數位翻譯的使用者撥號方案。 | -由 Microsoft 啟用。 <br> -系統管理員登入位址。 <br> -支援動態通話。 |
| 運算子連線 | -電信公司管理 PSTN 連接和 SBC。 <br> -不需要購買或管理 SBC。 | -透過電信公司取得。 <br> - 與電信公司管理的緊急位址相關聯的號碼。  | -由電信公司管理。 <br>-系統管理員設定數位翻譯的使用者撥號方案。 | -由電信公司啟用。 <br> -系統管理員登入位址。 <br> -支援動態通話。 |
| 直接路由 | -需要向協力廠商廠商購買經過認證的 SBC。<br>-連線 SBC Teams 電話。<br> -使用現有的 PSTN 電信公司。 | 透過電信公司取得。 | -需要系統管理員進行額外的配置。<br>-系統管理員設定號碼翻譯的主幹撥號方案。 <br>-LBR 可用於限制免付費路。 | -需要系統管理員進行額外的配置。 <br>-不支援已註冊的位址。 <br>-支援動態通話，但需要額外的配置。 |
|||||


### <a name="phone-number-management"></a>電話號碼管理

Microsoft 有兩種可用的電話號碼類型：訂閱者 (使用者) 號碼，可指派給貴組織的使用者，以及服務號碼，以付費和免付費服務號碼提供。 服務號碼的並行通話容量高於訂閱者號碼，並可以指派給音訊會議、自動語音服務或通話佇列等服務。

您必須決定：

- 哪些使用者位置需要 Microsoft 的新電話號碼？
- 我需要哪一 (或服務) 電話號碼？
- 如何將現有的電話號碼Teams？

您取得和管理電話號碼方式會根據您的 PSTN 連接選項而不同。

- 有關管理通話方案電話號碼的資訊，請參閱 [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 有關使用運算子管理電話號碼連線，請參閱使用運算子 連線[設定電話號碼](operator-connect-configure.md#set-up-phone-numbers)。

- 有關管理直接路由電話號碼的資訊，請參閱設定電話號碼並 [啟用企業語音和語音信箱](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。


### <a name="call-routing-and-dial-plans"></a>通話路由和撥號方案

您設定通話路由方式會根據您的 PSTN 連接選項而不同。  

- 針對通話方案，大部分的通話路由是由 Microsoft 通話方案基礎結構處理。 您可以設定使用者撥號方案，以用於電話授權和通話路由的號碼翻譯。 詳細資訊，請參閱 [什麼是撥號方案？](what-are-dial-plans.md)。

- 針對電信連線，大部分的通話路由是由電信公司管理。  您可以設定使用者撥號方案，以用於電話授權和通話路由的號碼翻譯。 詳細資訊，請參閱 [什麼是撥號方案？](what-are-dial-plans.md)。

- 針對直接路由，您必須指定語音路由並指派語音路由策略給使用者，來設定通話路由。 您可以在主幹層級設定號碼翻譯的撥號方案，以確保與會話邊界控制器和 SBC (互通性) 。 詳細資訊請參閱設定直接 [路由](direct-routing-voice-routing.md)的語音路由、 [管理語音路由策略](manage-voice-routing-policies.md) 和 [翻譯電話號碼](direct-routing-translate-numbers.md)。 


### <a name="location-based-routing-for-direct-routing"></a>Location-Based直接路由的路由

在某些國家和地區，忽略 PSTN 電信公司以降低長途通話費用是違法的行為。 Location-Based直接 (LBR) 路由選項可讓您根據使用者的地理位置Teams免付費。 若要進一步瞭解如何規劃及設定 LBR，請參閱下列文章：

- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [設定依位置路由的網路設定](location-based-routing-configure-network-settings.md)
- [啟用直接路由的依位置路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  說明一家虛構的多國公司 Contoso 如何為Location-Based路由實作。


### <a name="emergency-calling"></a>緊急電話

您設定緊急電話方式會根據您的 PSTN 連接選項而不同。

- 針對通話方案，每個使用者會自動啟用緊急通話，而且必須擁有與其指派的電話號碼相關聯的已註冊緊急位址。 支援 (用戶端Teams位置) 緊急電話。  

- 針對電信連線，每個使用者會自動啟用緊急電話，而且必須擁有與其指派的電話號碼相關聯的已註冊緊急位址，但只能由電信合作夥伴設定。 支援 (用戶端Teams位置) 緊急電話。

- 針對直接路由，您必須使用 Teams 緊急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 來定義緊急號碼及其相關聯的路由目的地，以定義使用者的緊急通話政策。 直接路由使用者不支援已註冊的緊急位置。 針對動態緊急電話，路由緊急電話時，可能需要進行其他組組，並可能還需要合作夥伴連接。

若要進一步瞭解緊急通話概念和術語，以及如何設定緊急電話和動態緊急電話，請參閱下列文章：

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md)
- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理直接路由的緊急通話路由策略](manage-emergency-call-routing-policies.md)
- [Contoso 案例研究：緊急電話](voice-case-study-emergency-calling.md)<br>
  說明一家虛構的多國公司 Contoso 如何為組織實作緊急電話。


### <a name="network-topology-for-voice-features"></a>語音功能的網路拓撲

如果您要部署動態緊急電話或直接路由Location-Based路由，您必須設定網路設定，以在 Microsoft Teams 中Microsoft Teams。 若要瞭解如何設定網路區域、網路網站、網路子網和受信任的 IP 位址的網路設定，請參閱下列文章：

- [雲端語音功能的網路設定Microsoft Teams概念和術語](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲Microsoft Teams](manage-your-network-topology.md)



