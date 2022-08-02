---
title: 瞭解閱讀進度建議的深入解析
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 瞭解如何在閱讀進度中使用深入解析資料，以協助改善學生的閱讀水準。
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157875"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>瞭解閱讀進度建議的深入解析

本文適用于想要瞭解深入解析資料如何用於閱讀進度建議的教育 IT 系統管理員。

深入解析可讓授課者使用閱讀進度追蹤學生的閱讀流暢性，此工具可記錄學生大聲朗讀並自動偵測錯誤。

閱讀進度提供下列類型的閱讀挑戰作業：

- **關聯式文字**：根據學生在上一次的朗讀進展作業中發音錯誤的字詞來練習建議的字詞。
- **相互關聯的單字**：根據有相同閱讀挑戰類型的學生常見錯誤來練習建議的字詞。

如需使用深入解析進行閱讀進度的授課者指導方針，請參閱 [使用深入解析建立閱讀進度挑戰作業](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe)。

## <a name="how-does-microsoft-recommend-correlated-words"></a>Microsoft 如何建議相互關聯的字詞？

相互關聯的字詞是個人化的，建議的字詞，而 Insights for Education 會將這些字視為不太適合其他有類似閱讀模式的學生。

相互關聯的字詞是以稱為「 **共同作業篩選**」的機器學習技巧為基礎。

- 深入解析會分析共用地理區域和語言的各個班級的學生閱讀資料，以識別學生難以使用的文字群組。

- 如果使用一組具挑戰性的字詞，[深入解析] 也會識別類似的叢集，並使用這些叢集來為學生推薦其他字詞以進行目標練習。

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>Microsoft 是否保護學生資料的私密性與安全性？

Microsoft 致力於以負責負責且合乎道德的方式使用資料。

以下是建立此功能所採取的一些措施：

- 學生資料分析是以眼外的方式建立，這表示 Microsoft 只能存取學生的閱讀資料，只能存取分析結果。

- 租使用者系統管理員可以關閉 [進階 [推斷] 切換開關](class-insights.md#turn-on-and-off-advanced-inferences-in-insights)，退出資料分析程式。

- 不適當的文字會從 **相互關聯的單字** 推薦清單中篩選掉。 這是透過結合資料科學技術和封鎖已知有問題的字詞來完成。 不過，此程式並非錯誤證明。 授課者應檢閱建議。

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>深入解析的字建議有哪些限制？

- [這些語言](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages)目前支援 Word 的朗讀進展建議。

- 相互關聯的字詞只會在班級中顯示，至少有五個學生已提交閱讀進度作業。

- 如果沒有任何學生有相似但不相同的錯誤模式，深入解析可能不建議使用新字詞。
