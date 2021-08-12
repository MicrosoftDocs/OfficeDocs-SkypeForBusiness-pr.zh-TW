---
title: 電話系統直接路由Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 瞭解直接路由組態、必要的核心部署決策，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55676d855d3e15c3f767203da981a4fae241f3128a270f5656d770a229f00059
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848068"
---
# <a name="phone-system-direct-routing"></a>電話直接路由

您已完成[開始使用](get-started-with-teams-quick-start.md)。 您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。 您可能已經部署會議 [&會議](deploy-meetings-microsoft-teams-landing-page.md)。 現在，您已準備好新增雲端語音工作負載，而且決定使用您自己的電話電信業者來使用 (PSTN) 直接路由電話系統連接。 透過直接路由，您就可以實際地透過任何電信運營公司使用電話系統。

本文將說明直接路由的核心部署決策，以及您可能想要根據貴組織的需求考慮的其他考慮。 您也應該在[Microsoft Teams中](cloud-voice-landing-page.md)閱讀雲端語音，以瞭解更多關於 Microsoft 雲端語音服務的資訊。

## <a name="learn-more-about-direct-routing"></a>深入瞭解直接路由

下列文章提供有關直接路由的電話系統資訊。 要配置直接路由，必須瞭解 PSTN 路由設計。 您應該閱讀所有這些文章，瞭解如何規劃及設定直接路由：

- [規劃直接路由](direct-routing-plan.md) 
- [設定直接路由](direct-routing-configure.md)
- [通過直接路由認證的工作階段邊界控制器清單](direct-routing-border-controllers.md)
- [監視和疑難排解直接路由](direct-routing-monitor-and-troubleshoot.md)

此外，根據您的需求，您可能會想要閱讀下列文章：

-  [設定多個租用戶的工作階段邊界控制器](direct-routing-sbc-multiple-tenants.md)
-  [移轉至直接路由](direct-routing-migrating.md)
-  [含有 PSTN 連線功能的混合式環境中的使用者帳戶](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 觀看下列會話以深入瞭解直接路由：[直接路由Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署決策

這些是直接路由應考慮的核心決策。 

|問問自己|動作 |
| :------------|:-------|
|我要為哪些使用者啟用直接路由？ | 詳細資訊，請參閱啟用 [使用者進行直接路由服務](direct-routing-configure.md)。 |
我是否擁有直接路由所需的授權？ | 詳細資訊，請參閱 [授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>會話邊界控制器 (SBC) 考慮

使用直接路由，您將自己的會話邊界控制器 (SBC) 直接電話系統。  有關認證 SBCs 的清單，請參閱 [支援的會話邊界控制器](direct-routing-border-controllers.md)。

|問問自己|動作 |
|:------------|:-------|
| 我要在哪裡以及如何部署 SBCs？ | 詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md) | 
我有多個租使用者嗎？ | 詳細資訊，請參閱為多個租使用者設定 [會話邊界控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>語音路由考慮

您必須設定電話電話系統將通話路由至特定的 SBC。

|問問自己|動作 |
|:------------|:-------|
| 我需要建立哪些語音路由策略、PSTN 使用量和語音路由？ | 若要瞭解語音路由資訊，請參閱 [設定語音路由](direct-routing-configure.md)。
| 哪些使用者會指派給我定義的語音路由策略？ | 請參閱設定語音 [路由中的範例](direct-routing-configure.md)。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy 確保Teams用戶端內接來電

直接路由僅支援Microsoft Teams。 若要透過直接路由接收 PSTN 通話，您必須設定 TeamsUpgradePolicy，以確保在 Teams。 使用者必須進入Teams模式，您可以指派 TeamsUpgradePolicy 的 「UpgradeToTeams」 實例給他們。 

|問問自己|動作 |
|:------------|:-------|
|僅Teams模式是什麼意思？ | 有關詳細資訊，請參閱將應用程式與 Teams一起使用 商務用 Skype 的組織[移商務用 Skype。](./migration-interop-guidance-for-teams-with-skype.md)|
|||

## <a name="additional-deployment-considerations"></a>其他部署考慮

您可能會想要根據貴組織的需求和組組來考慮下列事項：

| 問問自己| 動作 |
| :------------|:-------|
| 您是否有已商務用 Skype Server混合式連接的現有部署？ |  若要瞭解混合式環境中使用者帳戶的部署與管理方式，請參閱使用 PSTN 連接的混合 [式環境中的使用者帳戶](direct-routing-user-accounts-in-a-hybrid-environment.md)。| 
| 您是否從通話方案或內部部署商務用 Skype直接路由？ | 若要進一瞭解從現有環境移向直接路由，請參閱 [移遷移到直接路由](direct-routing-migrating.md)。 |
|||
