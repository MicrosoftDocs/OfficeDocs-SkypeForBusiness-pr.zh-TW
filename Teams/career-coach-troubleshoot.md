---
title: Microsoft Teams 的職涯教練疑難排解
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何疑難排解 Microsoft Teams 的職業教練中的常見問題。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024146"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Microsoft Teams 的職涯教練疑難排解

本文適用于需要針對 Microsoft Teams 的職涯教練進行疑難排解的教育版 IT 系統管理員。

以下是 IT 系統管理員使用職業教練可能採取的常見問題和解決步驟。

## <a name="missing-required-configuration-data"></a>遺失必要的組態資料

如果您在 [職涯教練] 體驗中看到「目前正在設定職涯教練，供您使用」，則 **尚未新增所有必要的組態資料**。

您 **必須先完成下列各節** ，才能使用職業教練：

- [品牌和喜好設定](career-coach-set-up-steps.md#brand-and-preferences)
- [LinkedIn連線](career-coach-set-up-steps.md#linkedin-connection)
- [課程目錄](career-coach-set-up-steps.md#course-catalog)
- [研究欄位](career-coach-set-up-steps.md#fields-of-study)

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

如果使用者的 Microsoft Teams 未顯示 [職涯教練]，則設定原則變更可能尚未生效。 在設定原則變更生效之前，Microsoft Teams 不會為使用者安裝和釘選職涯教練。 原則變更可能需要幾個小時才會生效。

不過，[職涯教練] 可以直接從 Microsoft Teams App Store 安裝。

- 如果使用者在 Microsoft Teams App Store 中找不到 [職涯教練]，請檢閱您的應用程式許可權原則，並確保 [職涯教練] 不是封鎖的應用程式。
- [職涯教練] 是一個 Microsoft 應用程式，最佳作法是依許可權原則允許 Microsoft 應用程式。 深入瞭解 [設定許可權原則](teams-app-permission-policies.md)。

## <a name="career-coach-initialization-isnt-complete"></a>職涯教練初始化尚未完成

您可能會遇到下列錯誤：「我們無法擷取應用程式的設定。 請再試一次。 如果您仍然遇到問題，請連絡 Microsoft 客戶支援」。

檢查 [[職涯教練] 設定頁面](career-coach-set-up-steps.md#career-coach-settings-status)上的 **[服務布建狀態**]。

如果您的租使用者仍在初始化狀態，請等候 15 分鐘，然後再試一次。 如果您仍然收到錯誤訊息，請開啟支援票證。
