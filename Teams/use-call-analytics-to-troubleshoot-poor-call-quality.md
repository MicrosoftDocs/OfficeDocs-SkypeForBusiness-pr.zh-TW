---
title: 使用通話分析來疑難排解通話品質不佳的問題
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用每個使用者的通話分析詳細資料，瞭解裝置、網路和連接能力，以疑難排解 Microsoft Teams 通話和會議的使用者問題。
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760558"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用通話分析來疑難排解通話品質不佳的問題

如果您是 Teams 系統管理員或 Teams 通訊支援專家或工程師，本文將說明如何使用通話分析疑難排解個別使用者的 Microsoft Teams 通話或會議品質不佳的問題。

## <a name="call-analytics-permissions"></a>通話分析許可權

本文假設您已經設定通話分析。 如果您沒有，請參閱設定 Teams [的通話分析](set-up-call-analytics.md)。

## <a name="introduction-to-call-analytics"></a>通話分析簡介

通話分析會顯示 Office 365 帳戶中每個使用者的 Teams 通話和會議的詳細資訊。 它包含裝置、網路、連接和通話品質 (任何一項資訊都可能是導致通話或會議品質不佳) 。 如果您上傳建築物、網站和租使用者資訊，也會針對每一個通話和會議顯示此資訊。 使用通話分析來説明您瞭解使用者為何通話或會議體驗不佳。

通話分析會顯示通話或會議的每一個區段 ，例如，從一個參與者到另一個參與者。 通過分析這些詳細資料，Teams 系統管理員可以隔離問題區域，並找出品質不佳的根本原因。

做為 Teams 系統管理員，您可以完全存取每個使用者的所有通話分析資料。 此外，您也可以指派 Azure Active Directory 角色給支援人員。 若要深入瞭解這些角色，請參閱授予支援 [與技術支援人員的許可權](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。 請勿錯過以下[每個 Teams 支援角色的作用？](#what-does-each-teams-support-role-do)

## <a name="where-to-find-per-user-call-analytics"></a>在哪裡可以找到每個使用者的通話分析

若要查看使用者的所有通話資訊和資料，請前往 [Teams 系統管理中心](https://admin.teams.microsoft.com)。 在 **使用者** 下，選取使用者，然後開啟& **設定檔** 頁面上的會議與通話清單。 您可以在這裡找到該使用者過去 30 天的所有通話和會議。

![所有分析使用者資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要取得特定會話的其他資訊 ，包括詳細的媒體和網路統計資料，請按一下會話以查看詳細資料。

![通話分析使用者會話資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>每個 Teams 支援角色的作用是什麼？

Teams **通訊支援專家 (** 第 1 層) 可處理基本通話品質問題。 他們不會調查會議的問題。 相反地，他們會收集相關資訊，然後升級為通訊支援工程師。

第 **2** 層支援 (Teams 通訊支援工程師) Teams 通訊支援專家所隱藏的詳細通話記錄中的資訊。 下表列出每個 Teams 通訊支援角色可用的資訊。

下表告訴您每個通訊支援角色可用的每個使用者資訊。

|活動|資訊|通訊內容<br>支援 *專家* 查看|通訊內容<br>支援 *工程師* 查看|
|---|---|---|---|
|**調用**|來電者名稱|只有代理程式搜尋的使用者名稱。|使用者名稱。|
||收件者名稱|以內部使用者或外部使用者顯示。|收件者名稱。|
||來電者電話號碼|除了最後三位數以外，整個電話號碼會以星號符號混淆。 例如，15552823 \* \* \* 。|除了最後三位數以外，整個電話號碼會以星號符號混淆。 例如，15552823 \* \* \* 。|
||收件者電話號碼|除了最後三位數以外，整個電話號碼會以星號符號混淆。 例如，15552823 \* \* \* 。|除了最後三位數以外，整個電話號碼會以星號符號混淆。 例如，15552823 \* \* \* 。|
||**通話詳細資料** \>**進位** 定位停駐點|未顯示資訊。|顯示的所有詳細資料，例如裝置名稱、IP 位址、子網映射等。|
||**通話詳細資料** \>**進位** \>**調試** 鍵|未顯示資訊。|顯示的所有詳細資料，例如 DNS 尾碼和 SSID。|
|**會議**|參與者名稱|只有代理程式搜尋的使用者名稱。 識別為內部使用者或外部使用者的其他參與者。|顯示所有名稱。|
||參與者計數|參與者人數。|參與者人數。|
||會話詳細資料|會話詳細資料以例外顯示。 只會顯示代理程式搜尋的使用者名稱。 識別為內部使用者或外部使用者的其他參與者。 電話號碼的最後三位數會以星號符號混淆。|顯示會話詳細資料。 顯示使用者名稱和會話詳細資料。 電話號碼的最後三位數會以星號符號混淆。|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>疑難排解使用者通話品質問題

1. 開啟 Teams 系統管理中心 <https://admin.teams.microsoft.com> () 您的 Teams 通訊支援或 Teams 系統管理員認證來登錄。

2. 在儀表板 **的** 使用者 **搜尋** 中，開始輸入您想要進行疑難排解之通話之使用者的名稱或 SIP 位址，或選取查看使用者以查看使用者清單。

3. 從清單中選取使用者。

4. 選取 **通話記錄**，然後選取您想要疑難排解的通話或會議。

5. 選取進 **一頁** ，然後尋找黃色和紅色專案，指出通話品質不佳或連接問題。

   在每個通話或會議的會議詳細資料中，次要問題會以黃色顯示。 如果某些專案是黃色，表示它超出正常範圍，而且可能會造成問題，但不太可能是問題的主要原因。 如果內容為紅色，這是一個嚴重的問題，而且可能是導致此會話通話品質不佳的主要原因。

在少數情況下，音訊會話不會收到體驗品質資料。 這通常是由中斷的通話或與用戶端的連線終止所導致。 發生此情況時，會話分級 **無法使用**。

如果音訊會話具有使用者體驗品質 (QoE) ，下表說明將會話視為不佳的主要 **問題**。

|問題|地區|描述|
|---|---|---|
|通話設定|會話|錯誤碼 Ms-diag 20-29 表示通話設定失敗。 使用者無法加入通話或會議。|
|音訊網路分類不良通話|會話|網路品質問題 (例如封包遺失、抖動、核OS 降級、RTT 或隱藏比) 發生。|
|裝置無法運作|裝置|裝置無法正常運作。 裝置無法運作的比例為： <p> DeviceRenderNotFunctioningEventRatio >= 0.005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0.005|
||||

## <a name="related-topics"></a>相關主題

[設定每個使用者的通話分析](set-up-call-analytics.md)
