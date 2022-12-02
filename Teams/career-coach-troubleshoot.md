---
title: 疑難排解 Teams Microsoft職涯教練
author: DaniEASmith
ms.author: danismith
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何疑難排解 Microsoft Teams 的 [職涯教練] 中的常見問題。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c00837c40fe405ab4d9d608326a12567843c8bb
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242447"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>疑難排解 Teams Microsoft職涯教練

本文適用于需要針對 Microsoft Teams 的職業教練進行疑難排解的教育版 IT 系統管理員。

以下是 IT 系統管理員使用職業教練可能採取的常見問題和解決步驟。

## <a name="missing-required-configuration-data"></a>遺失必要的組態資料

如果您在 [職涯教練] 體驗中看到「目前正在設定職涯教練，供您使用」，則 **尚未新增所有必要的組態資料**。

您的機構必須已完全設定 [LinkedIn聯](career-coach-set-up-steps.md#linkedin-connection-required) 機。

參考 [[職涯教練] 設定狀態](career-coach-set-up-steps.md#configuration-status) ，以查看哪些設定需要完成。

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>課程目錄或研究資料欄位的格式設定不正確

課程目錄和研究欄位的 CSV 具有必要的格式，最大大小為 18 MB。

參考 [職涯教練 [課程] 目錄檔架構](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) 和 [研究檔架構的](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) [職涯教練] 欄位，以確保設定正確。

此外，課程目錄檔案不應有超過 15，000 列以確保處理成功。

## <a name="missing-fields-in-career-coach-settings-pages"></a>[職涯教練] 設定頁面中遺失欄位

[職涯教練] 設定頁面需要欄位。 如果必要欄位尚未完成，頁面將不會提交。

您可能不會看到警告訊息，且無法提交頁面。

當您在頁面頂端看到綠色橫幅時，表示提交成功。

## <a name="setup-policy-changes-arent-complete"></a>安裝原則變更尚未完成

如果使用者無法在 Microsoft Teams 中顯示 [職涯教練]，則設定原則變更可能尚未生效。 在設定原則變更生效之前，將不會為 teams 中的使用者安裝和釘選職業教練Microsoft。 原則變更可能需要幾個小時才會生效。

不過，您可以直接從 Teams 應用程式商店Microsoft安裝職涯教練。

- 如果使用者在 Microsoft Teams 應用程式商店中找不到 [職涯教練]，請檢閱您的應用程式許可權原則，並確保 [職涯教練] 不是封鎖的應用程式。
- [職涯教練] 是Microsoft應用程式，最佳作法是依許可權原則允許Microsoft應用程式。 深入瞭解 [設定許可權原則](teams-app-permission-policies.md)。

## <a name="career-coach-initialization-isnt-complete"></a>職涯教練初始化尚未完成

您可能會遇到下列錯誤：「我們無法擷取應用程式的設定。 請再試一次。 如果仍然有問題，請連絡Microsoft客戶支援」。

檢查 [[職涯教練] 設定頁面](career-coach-set-up-steps.md#career-coach-settings-status)上的 **[服務布建狀態**]。

如果您的租使用者仍在初始化狀態，請等候 15 分鐘，然後再試一次。 如果您仍然收到錯誤訊息，請開啟支援票證。
