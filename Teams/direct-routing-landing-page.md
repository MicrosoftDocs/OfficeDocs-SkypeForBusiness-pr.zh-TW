---
title: 電話系統直向路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: 直接路由的登陸頁面
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dca9fda99973931cff70301da089f6d0c3f4a9c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236583"
---
# <a name="phone-system-direct-routing"></a>電話系統直向路由

您已完成[快速入門](get-started-with-teams-quick-start.md)。 您已在整個組織中利用[聊天、團隊、頻道、& 應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)來推出小組。 也許您已將[會議 & 會議](deploy-meetings-microsoft-teams-landing-page.md)已部署。 現在您已經準備好要新增雲端語音工作負載, 而您決定要使用自己的電話運營公司來取得公用交換電話網絡 (PSTN) 連線, 方法是使用 [電話系統直向] 路由。 透過直接路由, 您可以在幾乎任何電話運營商中使用電話系統。

本文將說明直接路由的核心部署決策, 以及您可能想要考慮的其他考慮因素 (視貴組織的需求而定)。 您也應該閱讀[Microsoft 團隊中的雲端語音](cloud-voice-landing-page.md), 以取得關於 Microsoft 雲端語音服務的詳細資訊。

## <a name="learn-more-about-direct-routing"></a>深入瞭解直接路由

下列文章提供有關設定和使用 [電話系統直接路由] 的詳細資訊。 設定直接路由需要瞭解 PSTN 路由設計。 您應該閱讀所有這些文章, 以瞭解如何規劃及設定直接路由:

- [規劃直接路由](direct-routing-plan.md) 
- [設定直接路由](direct-routing-configure.md)
- [認證以直接路由的會話邊界控制器清單](direct-routing-border-controllers.md)
- [監控並疑難排解直接路由](direct-routing-monitor-and-troubleshoot.md)

此外, 根據您的需求, 您可能會想要閱讀下列文章:

-  [針對多個承租人設定會話框線控制器](direct-routing-sbc-multiple-tenants.md)
-  [遷移至直接路由](direct-routing-migrating.md)
-  [具有 PSTN 連接的混合式環境中的使用者帳戶](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 觀看下列會話以深入瞭解直接路由: [Microsoft 團隊中的直接路由](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署決定

以下是直接路由所需考慮的核心決策。 

|問自己|執行 |
| :------------|:-------|
|我要對哪些使用者啟用直接路由？ | 如需詳細資訊, 請參閱[啟用直接路由服務的使用者](direct-routing-configure.md#enable-users-for-direct-routing-service)。 |
我是否有直接路由所需的授權？ | 如需詳細資訊, 請參閱[授權及其他需求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>會話邊界控制器 (SBC) 考慮

使用直接路由, 您可以直接將自己的會話邊界控制器 (SBC) 連線至 [電話系統]。  如需已驗證的 SBCs 清單, 請參閱[支援的會話框線控制器](direct-routing-border-controllers.md)。

|問自己|執行 |
|:------------|:-------|
| 我要如何部署 SBCs？ | 如需詳細資訊, 請參閱[設定直接路由](direct-routing-configure.md) | 
我有多個承租人嗎？ | 如需詳細資訊, 請參閱為[多個承租人設定會話框線控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>語音路由考慮

您必須設定 [電話系統], 將呼叫路由到特定的 SBCs。

|問自己|執行 |
|:------------|:-------|
| 我需要建立哪些語音路由策略、PSTN 使用及語音路由？ | 如需語音路由資訊, 請參閱[設定語音路由](direct-routing-configure.md#configure-voice-routing)。
| 系統會將哪些使用者指派給我定義的語音路由策略？ | 請參閱[設定語音路由](direct-routing-configure.md#configure-voice-routing)中的範例。 |
|||

### <a name="calling-and-interop-policies"></a>通話和交互操作原則

只有 Microsoft 團隊支援直接傳送。 若要透過直接佈線來撥打或接聽 PSTN 電話, 您必須設定必要的原則, 以確保在團隊中接收來電。 您可以將團隊設定為 [僅限團隊] 模式, 或將團隊設定為首選呼叫用戶端 (方法是指派 TeamsCallingPolicy 和 TeamsInteropPolicy), 以將團隊設定為呼叫的首選用戶端。

|問自己|執行 |
|:------------|:-------|
|我要如何將團隊設定為適用于通話的首選用戶端？ | 如需詳細資訊, 請參閱[將 Microsoft 團隊設定為使用者的首選呼叫用戶端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。|
|||

## <a name="additional-deployment-considerations"></a>其他部署考慮

根據貴組織的需求和設定, 您可能會想要考慮下列事項:

| 問自己| 執行 |
| :------------|:-------|
| 您是否有已設定混合式連線性的現有商務用 Skype 伺服器部署？ |  若要瞭解混合式環境中的使用者帳戶是如何提供和管理的, 請參閱[在具有 PSTN 連線的混合式環境中的使用者帳戶](direct-routing-user-accounts-in-a-hybrid-environment.md)。| 
| 您是否要從通話方案或商務用 Skype 內部部署環境直接傳送路線？ | 若要深入瞭解從現有環境遷移至直接路由的詳細資訊, 請參閱[遷移至直接路由](direct-routing-migrating.md)。 |
|||
