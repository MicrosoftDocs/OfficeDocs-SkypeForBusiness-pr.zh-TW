---
title: 使用通話分析來疑難排解不良通話品質
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用每個使用者的通話分析有關裝置、網路和連線能力的詳細資料，來疑難排解 Microsoft Teams 通話和會議的使用者問題。
ms.openlocfilehash: c83ecbad418dc471f1db2c9c71b88fa621fe4a11
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397094"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用通話分析來疑難排解不良通話品質

本文說明如果您擔任 Teams 系統管理員、Teams 通訊支援專家或 Teams 通訊支援工程師角色，如何使用 Call Analytics 針對個別使用者的 Microsoft Teams 通話或會議品質不佳問題進行疑難排解。

## <a name="call-analytics-permissions"></a>通話分析許可權

本文假設您已經設定「通話分析」。 如果您尚未設定，請閱讀 [設定 Teams 的通話分析](set-up-call-analytics.md)。

## <a name="introduction-to-call-analytics"></a>通話分析簡介

通話分析會顯示您Office 365帳戶中每個使用者的 Teams 通話和會議的詳細資訊。 它包含裝置、網路、連線能力和通話品質的相關資訊 (其中任何一項都可能是通話品質不佳或會議品質不佳) 的因素。 如果您上傳建築物、網站和租使用者資訊，這些資訊也會顯示在每個通話和會議中。 使用「通話分析」來協助您找出使用者通話或會議體驗不佳的原因。

通話分析會顯示通話或會議的每一段，例如，從一位參與者到第二位參與者。 透過分析這些詳細資料，Teams 系統管理員可以隔離問題區域，並找出品質不佳的根本原因。

身為 Teams 系統管理員，您可以完整存取每個使用者的所有通話分析資料。 此外，您可以指派 Azure Active Directory 角色來支援員工。 若要深入瞭解這些角色，請參閱 [授與許可權給支援人員和技術服務人員](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。 請勿錯過[下方每個 Teams 支援角色的作用為何？](#what-does-each-teams-support-role-do)

## <a name="where-to-find-per-user-call-analytics"></a>哪裡可以找到個別使用者的通話分析

若要查看使用者的所有通話資訊和資料，請移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。 在 [ **使用者**] 底下，選取使用者，然後開啟使用者設定檔頁面上的 **[會議&通話** ] 索引標籤。 您可以在這裡找到該使用者過去 30 天的所有通話和會議。

![所有分析使用者資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要取得特定會話的其他相關資訊，包括詳細的媒體和網路統計資料，請按一下會話以查看詳細資料。

![通話分析使用者會話資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

這段影片將示範檢視使用者會議和通話資訊的步驟。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53x2e?autoplay=false]

## <a name="what-does-each-teams-support-role-do"></a>每個 Teams 支援角色的功能為何？

**Teams 通訊支援專家** (層級 1 支援) 處理基本的通話品質問題。 它們不會調查會議的問題。 相反地，他們會收集相關資訊，然後向上呈報給 Teams 通訊支援工程師。

第 2 層支援服務 (**Teams 通訊支援工程師**) 看到 Teams 通訊支援專家隱藏的詳細通話記錄中的資訊。 下表列出每個 Teams 通訊支援角色可用的資訊。

下表告訴您每個通訊支援角色可使用哪些個別使用者資訊。

|活動|資訊|通訊內容<br>支援 *專員* 會看到|通訊內容<br>支援 *工程師* 會看到|
|---|---|---|---|
|**調用**|來電者名稱|僅搜尋專員所搜尋之使用者的名稱。|使用者名稱。|
||收件者名稱|顯示為內部使用者或外部使用者。|收件者名稱。|
||來電者電話號碼|除了最後三位數以外，整個電話號碼都會與星號符號混淆。 例如，15552823 \* \* \* 。|除了最後三位數以外，整個電話號碼都會與星號符號混淆。 例如，15552823 \* \* \* 。|
||收件者電話號碼|除了最後三位數以外，整個電話號碼都會與星號符號混淆。 例如，15552823 \* \* \* 。|除了最後三位數以外，整個電話號碼都會與星號符號混淆。 例如，15552823 \* \* \* 。|
||**通話詳細資料** \>**[進階] 索引** 標籤|未顯示資訊。|所有顯示的詳細資料，例如裝置名稱、IP 位址、子網對應等等。|
||**通話詳細資料** \>**先進** \>**[偵錯] 索引卷** 標|未顯示資訊。|顯示的所有詳細資料，例如 DNS 尾碼和 SSID。|
|**會議**|參與者名稱|僅搜尋專員所搜尋之使用者的名稱。 其他識別為「內部使用者」或「外部使用者」的參與者。|顯示所有名稱。|
||參與者計數|參與者數目。|參與者數目。|
||會話詳細資料|除了例外，顯示會話詳細資料。 僅顯示專員搜尋的使用者名稱。 其他識別為「內部使用者」或「外部使用者」的參與者。 電話號碼的最後三位數與星號符號混淆。|顯示會話詳細資料。 顯示使用者名稱和會話詳細資料。 電話號碼的最後三位數與星號符號混淆。|
||||

> [!NOTE]
> [進階] 索引標籤的 [其他] 區段和 [偵錯] 索引標籤所包含的資訊包含遙測和服務診斷資料，意在協助 Microsoft 支援工程師。 如果沒有支援工程師可用之額外資料的內容，這些資料看起來可能多餘、不正確或令人混淆。 雖然我們讓進階使用者能夠在疑難排解通話問題中尋找其他層級的詳細資料，但我們不建議在沒有 Microsoft 支援的情況下根據此資料做出判斷。

## <a name="troubleshoot-user-call-quality-problems"></a>疑難排解使用者通話品質問題

1. 開啟 Teams 系統管理中心 (<https://admin.teams.microsoft.com>) 並使用您的 Teams 通訊支援或 Teams 系統管理員認證登入。

2. 在 **儀表板** 的 [ **使用者搜尋**] 中，開始輸入您要進行疑難排解之使用者的名稱或 SIP 位址，或選取 [ **檢視使用者** ] 以查看使用者清單。

3. 從清單中選取使用者。

4. 選取 **[通訊記錄**]，然後選取您要進行疑難排解的通話或會議。

5. 選取 [ **進階** ] 索引標籤，然後尋找指出通話品質不佳或連線問題的黃色和紅色專案。

   在每個通話或會議的會話詳細資料中，小問題會以黃色顯示。 如果某個專案是黃色，表示它超出一般範圍，而且可能造成問題，但不太可能是問題的主要原因。 如果出現紅色專案，則表示這是嚴重的問題，且可能是此會話通話品質不佳的主要原因。

在少數情況下，音訊會話不會收到體驗品質資料。 這通常是由通話中斷或與用戶端的連線終止所導致。 發生這種情況時，會話分級 **就無法使用**。

針對確實具備體驗品質 (QoE) 資料的音訊會話，下表說明將會話資格視為 **不佳** 的主要問題。

|問題|地區|描述|
|---|---|---|
|通話設定|會話|Ms-diag 20-29 錯誤碼表示通話設定失敗。 使用者無法加入通話或會議。|
|音訊網路分類為不良通話|會話|發生封包遺失、抖動、NMOS 降級、RTT 或隱藏比例等 (網路品質問題) 。|
|裝置無法運作|裝置|裝置無法正常運作。 裝置無法運作的比例如下： <p> DeviceRenderNotFunctioningEventRatio >= 0.005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0.005|
||||

## <a name="related-topics"></a>相關主題

[設定每個使用者的通話分析](set-up-call-analytics.md)
