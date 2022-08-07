---
title: 直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 瞭解 Teams Phone System 搭配直接路由。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff97fc683acd693f867126661c9bf90550ebbe5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269918"
---
# <a name="direct-routing"></a>直接路由

您已完成[開始使用](get-started-with-teams-quick-start.md)。 您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。 您可能已部署 [會議&會議](deploy-meetings-microsoft-teams-landing-page.md)。 現在您已準備好新增語音工作負載，而且您決定使用自己的電話語音電信業者來進行公用交換電話網路 (PSTN) 連線，方法是使用電話系統搭配直接路由。 透過直接路由，您就可以實際地透過任何電信運營公司使用電話系統。

本文將說明直接路由的核心部署決策，以及您可能想要根據組織需求考慮的其他考慮。 如需 Microsoft 語音服務的詳細資訊，您也應該閱讀 [規劃您的語音解決方案](cloud-voice-landing-page.md) 。

## <a name="learn-more-about-direct-routing"></a>深入瞭解直接路由

下列文章提供設定和使用直接路由的詳細資訊。 設定直接路由需要瞭解 PSTN 路由設計。 您應該閱讀所有這些文章，以瞭解如何規劃及設定直接路由：

- [規劃直接路由](direct-routing-plan.md) 
- [設定直接路由](direct-routing-configure.md)
- [通過直接路由認證的工作階段邊界控制器清單](direct-routing-border-controllers.md)
- [監視和疑難排解直接路由](direct-routing-monitor-and-troubleshoot.md)

此外，您可能會想要根據需求閱讀下列文章：

-  [設定多個租用戶的工作階段邊界控制器](direct-routing-sbc-multiple-tenants.md)
-  [移轉至直接路由](direct-routing-migrating.md)
-  [含有 PSTN 連線功能的混合式環境中的使用者帳戶](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 請觀看下列會話以深入瞭解直接路由： [Microsoft Teams 中的直接路由](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署決策

這些是直接路由的核心決策。 

|問問自己|動作 |
| :------------|:-------|
|我會針對哪些使用者啟用直接路由？ | 如需詳細資訊，請參閱 [啟用使用者的直接路由服務](direct-routing-configure.md)。 |
我是否擁有直接路由所需的授權？ | 如需詳細資訊，請參閱 [授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>會話框線控制器 (SBC) 考慮

透過直接路由，您可以將自己的會話框線控制器 (SBC) 直接連接到電話系統。 如需認證 SB 的清單，請參閱 [支援的會話框線控制器](direct-routing-border-controllers.md)。

|問問自己|動作 |
|:------------|:-------|
| 部署 SBC 的位置與方式為何？ | 如需詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md) | 
我是否有多個租使用者？ | 如需詳細資訊，請參閱 [為多個租使用者設定會話框線控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>語音路由考慮

您必須設定 [電話系統]，將通話路由至特定的 SBC。

|問問自己|動作 |
|:------------|:-------|
| 我需要建立哪些語音路由原則、PSTN 使用方式和語音路由？ | 如需語音路由資訊，請參閱 [設定語音路由](direct-routing-configure.md)。
| 將指派哪些使用者到我定義的語音路由原則？ | 請參閱設定 [語音路由](direct-routing-configure.md)中的範例。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy 確保來電可撥入 Teams 用戶端

直接路由僅支援 Microsoft Teams。 若要透過直接路由接聽 PSTN 電話，您必須設定 TeamsUpgradePolicy 以確保在 Teams 中收到來電。 使用者必須處於 TeamsOnly 模式，您可以指派 TeamsUpgradePolicy 的 「UpgradeToTeams」實例給他們。 

|問問自己|動作 |
|:------------|:-------|
|TeamsOnly 模式代表什麼意思？ | 如需詳細資訊，請參閱[使用 Teams 與商務用 Skype的組織移轉和互通性指導方針](./migration-interop-guidance-for-teams-with-skype.md)。|
|||


