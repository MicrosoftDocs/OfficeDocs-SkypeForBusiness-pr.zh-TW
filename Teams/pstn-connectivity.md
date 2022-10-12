---
title: PSTN 連線選項
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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 深入瞭解 Teams 通話 (PSTN 連線) 選項，以及您為組織做出的決策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 974418a6a1cf963b66b1f0a8667c5ed75b73f72b
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551697"
---
# <a name="pstn-connectivity-options"></a>PSTN 連線選項

Microsoft 透過電話系統為貴組織提供完整的 Private Branch Exchange (PBX) 功能。 不過，若要讓使用者在組織外部撥打電話，您需要將電話系統連線到公用交換電話網路 (PSTN) 。

本文著重于 PSTN 連線選項。 如需 Microsoft 語音解決方案的詳細資訊，包括電話系統功能的詳細資料，請參閱 [規劃您的 Teams 語音解決方案](cloud-voice-landing-page.md)。

若要將電話系統連線到 PSTN，您可以選擇下列選項：

- [**通話方案**](#phone-system-with-calling-plan)。 將 Microsoft 做為 PSTN 電信業者的所有雲端解決方案。

- [**運算子連線**](#phone-system-with-operator-connect)。 使用運算子連線時，如果您現有的電信業者參與 Microsoft 運算子連線計畫，他們可以管理 PSTN 通話和會話框線控制器 (SBC) 。

- [**Teams Phone Mobile**](#phone-system-with-teams-phone-mobile)。 使用 Microsoft Teams 電話 Mobile，使用者啟用 SIM 卡的電話號碼也會是他們的 Teams 電話號碼。 如果您現有的電信業者參與Microsoft Teams 電話行動裝置計畫，他們可以管理將 PSTN 通話帶到 Teams 的服務。  

- [**直接路由**](#phone-system-with-direct-routing)可讓您使用自己的 PSTN 電信業者，方法是將會話框線控制器 (的)  (SBC) 連線至電話系統。

您也可以選擇選項群組合，讓您設計複雜環境的解決方案，或管理多步驟移轉。

您選擇的選項或選項會影響部分手機系統功能的設定方式。 如需詳細資訊，請參閱本文稍後 [的設定考慮](#configuration-considerations) 。

## <a name="phone-system-with-calling-plan"></a>電話系統與通話方案

電話系統與通話方案是 Microsoft 適用于 Teams 使用者的全雲語音解決方案。 此解決方案是將電話系統連線到 PSTN 的最簡單選項。 使用此選項，Microsoft 會做為您的 PSTN 電信業者，如下圖所示：

![圖表 1 顯示電話系統與通話方案。](media/voice-solutions-simple.png)

如果您對下列事項回答「是」，則「電話系統與通話方案」是適合您的解決方案：

- 您所在的地區可使用通話方案。
- 您不需要保留目前的 PSTN 電信業者。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

使用此選項：

- 您可以取得已新增國內或國際通話方案的電話系統，這些方案可根據授權) 的服務層級 (來撥打全球各地的電話。

- 您不需要部署或維護內部 &mdash; 部署，因為通話方案在 Microsoft 365 外運作。

- 注意：您可以透過直接路由連接支援的會話框線控制器 (SBC) ，以便與協力廠商 PBX、類比裝置以及 SBC 支援的其他電話語音設備進行交互操作。

此選項需要與 Microsoft 365 的不間斷連線。

如需通話方案的詳細資訊，請參閱下列文章：

- [哪一個通話方案適合您？](calling-plan-landing-page.md)
- [如何購買通話方案](calling-plans-for-office-365.md)
- [通話方案的適用國家與地區](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [設定通話方案](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>電話系統與運算子連線

使用運算子連線時，如果您現有的電信業者參與 Microsoft 運算子連線計畫，他們就可以管理將 PSTN 通話帶到 Teams 的服務。 您的電信業者會 (SBC) 管理 PSTN 通話服務和會話框線控制器，讓您能夠儲存在硬體購買和管理上。

如果下列情況，運算子連線可能是您組織的正確解決方案：

- 您的地理位置無法使用 Microsoft 通話方案。
- 您慣用的電信業者是 Microsoft 運算子連線計畫的參與者。
- 您想要尋找新的電信業者，以便在 Teams 中啟用通話。

如需運算子連線的優點與需求資訊，以及參與此計畫的電信業者清單，請參閱 [規劃運算子連線](operator-connect-plan.md)。 如需如何設定運算子連線的相關資訊，請參閱 [設定運算子連線](operator-connect-configure.md)。

## <a name="phone-system-with-teams-phone-mobile"></a>含 Teams Phone Mobile 的電話系統

如果您現有的電信業者參與Microsoft Teams 電話行動裝置計畫，他們可以管理將 PSTN 通話帶到 Teams 的服務。 使用 Teams Phone Mobile 時，使用者的 SIM 卡手機號碼也是其 Teams 電話號碼。  使用者可以在 Microsoft Teams 的行動服務和電話線路上使用單一電話號碼。  

您可以考慮使用一組服務。 例如，您可以針對需要行動支援的銷售和現場組織，選擇 Teams Phone Mobile，但另一個解決方案適用于依賴電話機的現場話務中心組織。 

如果下列情況，Teams Phone Mobile 可能是您組織的正確解決方案：

- 您想要將 Teams Phone 的主要公司擁有、啟用 SIM 卡的行動電話號碼當做單一數位解決方案使用。
- 您慣用的電信業者是 Microsoft Teams 電話 Mobile 程式的參與者。
- 您想要尋找新的運算子，以便在 Teams 中啟用通話。

如需 Teams Phone Mobile 權益與需求的相關資訊，以及參與此計畫之電信業者的連結，請參閱 [規劃 Teams Phone Mobile](operator-connect-mobile-plan.md)。 如需如何設定 Teams Phone Mobile 的相關資訊，請參閱設定 [Teams Phone Mobile](operator-connect-mobile-configure.md)。

## <a name="phone-system-with-direct-routing"></a>具有直接路由的電話系統

此選項會使用直接路由將電話系統連線到電話語音網路，如下圖所示： 

![圖表 5 顯示電話系統與直接路由。](media/voice-solution-with-direct-routing.png)

如果您對下列問題回答「是」，那麼「具有直接路由的電話系統」是適合您的解決方案：

- 您想要搭配手機系統使用 Teams。
- 您必須保留目前的 PSTN 電信業者。
- 您想要混合路由，有些通話會透過通話方案進行，有些則是透過電信業者。
- 您需要與協力廠商 PBX 和/或設備相交互操作，例如重頭頁機、類比裝置等。

使用此選項：

- 您將自己支援的會話框線控制器 (SBC) 連線到電話系統，而不需要其他內部部署軟體。

- 您幾乎可以搭配電話系統使用任何電話語音電信業者。

- 您可以設定和管理此選項，也可以由您的電信業者或合作夥伴設定和管理， (詢問您的電信業者或合作夥伴是否提供此選項) 。

- 您可以在電話語音設備 &mdash; 之間設定互通性，例如協力廠商 PBX 和類比裝置 &mdash; ，以及電話系統。

此選項需要下列專案：

- 與 Microsoft 365 的連線不中斷。

- 部署及維護支援的 SBC。

- 與協力廠商電信業者簽訂的合約。
   (除非部署為提供連線到協力廠商 PBX、類比裝置或其他電話語音設備的選項，以供使用通話方案的電話系統使用者使用。) 

如需直接路由的詳細資訊，請參閱下列文章：

- [規劃直接路由](direct-routing-plan.md)
- [設定直接路由](direct-routing-configure.md)
- [管理語音路由原則以搭配直接路由使用](manage-voice-routing-policies.md)
- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [通過直接路由認證的工作階段邊界控制器清單](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>設定考慮

無論您選擇的 PSTN 連線選項為何，大部分的電話系統功能都相同。 例如，未接聽的通話和轉接設定、來電轉接、保留自訂音樂、通話駐留、共用行和語音應用程式皆可使用。 如需電話系統功能的完整清單，請參閱 [電話系統提供您可取得的](here-s-what-you-get-with-phone-system.md)功能。

不過，功能有一些差異會影響您設定特定電話系統功能的方式。 例如，直接路由需要其他步驟來設定通話路由。 另一個範例是，直接路由提供以位置為基礎的路由 (LBR) 。 LBR 可讓您在不允許付費的特定地理位置限制略過付費。 

下表醒目提示主要設定的差異。 表格後面的各節提供詳細資訊和詳細資料的連結。

| 選項 | 描述 | 電話號碼管理 | 通話路由 | 緊急通話可用性 |
| :------------| :-------| :-------| :-------| :-------| 
| 通話方案 | -Microsoft 做為 PSTN 電信業者。<br>-您不需要購買或管理 SBC。| 透過 Microsoft 取得。| -由 Microsoft 管理。 <br> -管理員設定號碼翻譯的使用者撥號對應表。 | -由 Microsoft 啟用。 <br> -管理員登錄位址。 <br> -支援動態通話。 |
| 運算子連線 | -電信業者會管理 PSTN 連線和 SBC。 <br> -您不需要購買或管理 SBC。 | -透過電信業者取得。 <br> - 與電信業者管理的緊急位址相關聯的數位。 | -由電信業者管理。 <br>-管理員設定號碼翻譯的使用者撥號對應表。 | -由電信業者啟用。 <br> -管理員登錄位址。 <br> -支援動態通話。 |
| Teams Phone Mobile | -電信業者會管理SIM-Enabled行動號碼、PSTN 連線能力和 SBC。 <br> -您不需要購買或管理 SBC。 | -透過電信業者取得。 <br> -與電信業者管理的緊急位址相關聯的數位。 | -由電信業者管理。 <br> 管理員設定號碼翻譯的使用者撥號對應表。 |- 由電信業者啟用。 <br> - 管理員登錄位址。 <br> - 支援動態通話。 <br> - 電信業者支援的原生撥號器緊急通話。 |
| 直接路由 | -需要向協力廠商廠商購買通過認證的 SBC。<br>-將您的 SBC 連線到電話系統。<br> -使用您現有的 PSTN 電信業者。 | 透過電信業者取得。 | -需要由系統管理員進行額外設定。<br>-管理員設定號碼翻譯的主幹撥號對應表。 <br>-LBR 可用來限制略過付費。 | -需要由系統管理員進行額外設定。 <br>-不支援登錄位址。 <br>-支援動態通話，但需要其他設定。 |


### <a name="phone-number-management"></a>電話號碼管理

Microsoft 有兩種類型的電話號碼可供使用：訂閱者 (使用者) 號碼，可以指派給貴組織中的使用者，以及提供付費和免付費服務號碼的服務號碼。 服務號碼的並行通話容量高於訂閱者號碼，而且可以指派給音訊會議、自動語音應答或通話佇列等服務。

您必須決定：

- 哪些使用者位置需要 Microsoft 的新電話號碼？
- 我需要訂閱者或服務 (電話號碼類型) ？
- 如何?將現有的電話號碼移轉到 Teams 嗎？

您取得及管理電話號碼方式會根據您的 PSTN 連線選項而有所不同。

- 如需管理通話方案電話號碼的相關資訊，請參閱 [管理通話方案的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 如需使用運算子連線管理電話號碼的相關資訊，請參閱 [使用運算子連線設定電話號碼](operator-connect-configure.md#set-up-phone-numbers)。

- 如需使用 Teams Phone Mobile 管理電話號碼的相關資訊，請參閱 [使用 Teams Phone Mobile 設定電話號碼](operator-connect-mobile-configure.md#set-up-phone-numbers)。

- 如需管理直接路由電話號碼的相關資訊，請參閱設定 [電話號碼並啟用企業語音](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。

### <a name="call-routing-and-dial-plans"></a>通話路由和撥號對應表

您設定通話路由方式會根據 PSTN 連線選項而有所不同。  

- 針對通話方案，大部分的通話路由是由 Microsoft 通話方案基礎結構處理。 您設定使用者撥號對應表，用於電話授權和通話路由的號碼轉換目的。 如需詳細資訊，請參閱[什麼是撥號對應表？](what-are-dial-plans.md)

- 針對運算子連線和 Teams Phone Mobile，大部分的通話路由是由電信業者管理。 您設定使用者撥號對應表，用於電話授權和通話路由的號碼轉換目的。 如需詳細資訊，請參閱[什麼是撥號對應表？](what-are-dial-plans.md)

- 若是直接路由，您必須指定語音路由，並將語音路由原則指派給使用者，藉此設定通話路由。 您可以在主幹層級設定撥號對應表，以確保可與會話框線控制器 (SBC) 互通性。 如需詳細資訊，請參閱設定 [直接路由的語音路由](direct-routing-voice-routing.md)、 [管理語音路由原則](manage-voice-routing-policies.md) 和 [翻譯電話號碼](direct-routing-translate-numbers.md)。 

### <a name="location-based-routing-for-direct-routing"></a>Location-Based直接路由的路由

在某些國家與地區，略過 PSTN 電信業者以降低長途電話成本是很非法的。 Location-Based直接路由的路由 (LBR) 可讓您根據 Teams 使用者的地理位置，限制其略過付費。 如需如何規劃及設定 LBR 的詳細資訊，請參閱下列文章：

- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [設定依位置路由的網路設定](location-based-routing-configure-network-settings.md)
- [啟用直接路由的依位置路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  說明虛擬的多國公司 Contoso 如何為組織實作Location-Based路由。

### <a name="emergency-calling"></a>緊急電話

您設定緊急電話的設定方式會根據您的 PSTN 連線選項而有所不同。

- 針對通話方案，系統會自動為每位使用者啟用緊急通話。 使用者必須有與其指派的電話號碼相關聯的已註冊緊急位址。 根據 Teams 用戶端) 的位置 (動態緊急通話。 如需詳細資訊，請參閱 [通話方案的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

- 針對運算子連線，系統會自動為每位使用者啟用緊急通話。 使用者必須有與其指派的電話號碼相關聯的已註冊緊急位址。 根據 Teams 用戶端) 的位置 (動態緊急通話。 如需詳細資訊，請參閱 [運算子連線的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect)。 

- 針對 Teams Phone Mobile，系統會自動為每個使用者啟用緊急通話。 緊急電話會自動傳送至 Teams Phone Mobile 電信業者，以取得指定號碼。 根據 Teams 用戶端) 的位置 (動態緊急通話。 如需詳細資訊，請參閱 [Teams Phone Mobile 的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-teams-phone-mobile)。 

- 若是直接路由，您必須使用 Teams 緊急通話路由原則 (TeamsEmergencyCallRoutingPolicy) ，來定義使用者的緊急通話原則。 原則會定義緊急號碼及其相關聯的路由目的地。 已註冊的緊急位置不支援直接路由使用者。 針對動態緊急通話，必須進行額外的設定，才能路由緊急電話，也可能用於合作夥伴連線。 如需詳細資訊，請參閱 [直接路由的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。

#### <a name="for-more-information"></a>如需詳細資訊

如需緊急通話概念與術語，以及如何設定緊急電話和動態緊急電話的詳細資訊，請參閱下列文章：

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md)
- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理直接路由的緊急通話路由原則](manage-emergency-call-routing-policies.md)
- [Contoso 案例研究：緊急通話](voice-case-study-emergency-calling.md)<br>
  說明虛擬的多國公司 Contoso 如何為組織實作緊急通話。

### <a name="network-topology-for-voice-features"></a>語音功能的網路拓撲

如果您要部署動態緊急通話或Location-Based直接路由路由，您必須在 Microsoft Teams 中為這些功能設定網路設定。 若要瞭解如何設定網路區域、網路網站、網路子網及受信任 IP 位址的網路設定，請參閱下列文章：

- [Microsoft Teams 中雲端語音功能的網路設定 - 概念與術語](cloud-voice-network-settings.md)
- [在 Microsoft Teams 中管理雲端語音功能的網路拓撲](manage-your-network-topology.md)
