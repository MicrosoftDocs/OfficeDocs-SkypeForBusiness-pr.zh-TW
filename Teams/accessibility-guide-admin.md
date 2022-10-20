---
title: Microsoft Teams 系統管理員的協助工具指南
ms.author: meghan
author: meganrmhan
ms.reviewer: eljones
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 開啟輔助字幕和轉譯、讓會議存取手語翻譯人員和 CART 輔助字幕、減少干擾、提高參與度，以及共用資源，以改善 Microsoft Teams 中的協助工具。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- M365-collaboration
ms.openlocfilehash: 7b089785695e9bef985107b5f1db8e5659c48c33
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614709"
---
# <a name="accessibility-guide-for-microsoft-teams-admins"></a>Microsoft Teams 系統管理員的協助工具指南

身為貴組織的 Microsoft Teams 系統管理員，您可以協助讓您的 Teams 環境盡可能具有包容性且易於所有使用者存取。 請遵循下列指南和資源來設定 Microsoft Teams 以獲得最佳協助工具。

> [!NOTE]
> 許多協助工具選項預設為開啟，但您可以依照本指南中的步驟，檢查它們是否未關閉。

## <a name="turn-on-captions-and-transcription-for-meetings-and-calls"></a>開啟會議和通話的輔助字幕和轉譯

為殘障使用者建立含包容性的會議和通話，讓每個人都能參與並參與。

### <a name="turn-on-live-captions-for-meetings"></a>開啟會議的即時輔助字幕

即時輔助字幕是會議中所描述內容的即時自動產生文字。 對於已開啟且未儲存的使用者，它們一次會顯示幾行。

若要為使用者開啟即時輔助字幕：

1. 在 Microsoft Teams 系統管理中心，移至 [ **會議]**，然後選取下拉式 **會議原則**。

2. 選取您要修改的原則。

3. 移至 [ **參與者&來賓** ] 區段。

4. 將 **即時輔助字幕** 切換為 **[未啟用]，但使用者可以覆寫**。

5. 選取 [儲存 **]**。

> [!TIP]
> 分享下列連結，讓使用者瞭解如何 [在會議期間開啟即時輔助字幕](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)。

> [!NOTE]
> 即時輔助字幕適用于在商業中舉行的會議，以及美國政府社群雲端 (GCC) 組織。

### <a name="turn-on-transcription-for-calls"></a>開啟通話轉譯

轉譯是自動產生、已錄製的通話內容文字。 開啟時，使用者可以在通話結束後檢閱文字記錄。

若要開啟使用者的轉譯：

1. 在 Microsoft Teams 系統管理中心，移至 **[語音**]，然後選取下拉式 **通話原則**。

2. 選取您要修改的原則。

3. 將 **轉譯** 轉換為 [ **開啟**]，然後選取 [ **儲存]**。

### <a name="why-captions-and-transcripts-are-important"></a>為什麼輔助字幕和文字記錄很重要

字幕和文字記錄是某人正在說話的文字版本。 除了音訊之外，他們也可以讓人員選擇查看文字，或是只查看音訊。 輔助字幕也可讓聽障或聽力不佳的使用者獲得額外資訊，以瞭解某些使用者從他們可能使用之手語翻譯或 CART 字幕所接收到的字幕。

字幕和轉譯在各種情況下都很有説明，但對下列情況特別有説明：

- 人員聽障或聽力不佳的使用者

- 學習障礙人員

- 人員在吵雜或分心的環境中，需要檢閱會議結束後分享的資訊

如需詳細資訊，請參閱下列連結：

- [錄製和轉譯的會議原則設定](/Microsoftteams/meetings-policies-recording-and-transcription)

- [WCAG) 1.2.4. (Web 內容協助工具指導方針：標題 (Live) ](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

## <a name="give-meeting-access-to-sign-language-interpreters-and-cart-communication-access-real-time-translation-captioners"></a>讓會議存取手語翻譯人員和 CART (Communication Access 即時翻譯) 字幕

讓手語翻譯人員和 CART (通訊存取即時翻譯，) 輔助字幕者可存取 Microsoft Teams 會議，以便能更有效地與聽障或聽力不佳的使用者共同作業。

### <a name="admit-sign-language-interpreters-and-cart-captioners-to-meetings"></a>准許手語解譯程式和 CART 字幕者加入會議

手語解譯程式和 CART 字幕可能不適用於您的組織，但您可以 [提供來賓存取權](/MicrosoftTeams/guest-access)，邀請他們加入 Microsoft Teams 會議。

允許來賓存取後，允許手語翻譯和 CART 字幕者進入會議：

1. 在 Microsoft Teams 系統管理中心，移至 [ **會議]**，然後選取下拉式 **會議原則**。

2. 選取您要修改的原則。

3. 移至 [ **參與者&來賓** ] 區段。

4. 在 [ **自動准許** 最符合貴組織合規性與安全性需求的人員] 底下選擇選項。 您可以選取下列其中一個選項：

   - 不建議 (所有人) 

   - 我組織中的人員和來賓 (建議) 

   - 組織中的人員、信任的組織和來賓

   - 組織中的人員

   - 僅限召集人

   - 僅邀請的使用者

5. 選取 [儲存 **]**。

> [!NOTE]
> [ **自動准許人員** ] 設定不適用於撥入使用者。

### <a name="turn-on-ip-video-feed-for-your-users"></a>為您的使用者開啟 IP 視訊摘要

讓手語翻譯人員能夠在 Microsoft Teams 會議期間共用 IP 視訊摘要，以便與聽障或聽力不佳的使用者通訊。

若要檢查 IP 視訊摘要是否已開啟：

1. 在 Microsoft Teams 系統管理中心，移至 [ **會議]**，然後選取下拉式 **會議原則**。

2. 選取您要修改的原則。

3. 移至 **[音訊&視訊** 一節。

4. 檢查 **IP 視****訊是否已** 開啟，然後選取 [儲存 **]**。

> [!TIP]
> 與使用者共用下列連結，讓他們可以調整使用 Teams 的方式，以最大化參與會議、專注和共同作業的能力：
> - [自訂會議檢視](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)
> - [使用 CART 標號](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

### <a name="why-its-important-to-include-sign-language-interpreters-and-cart-captioners"></a>為什麼加入手語翻譯和 CART 字幕很重要

有些使用者可能會偏好使用 CART 輔助字幕，因為他們可以比自動產生的輔助字幕更準確的特定行話、輔色等等。

主要通訊方法為手語的使用者，需要手語解譯，而必須有人為翻譯人員才能使用。

如需詳細資訊，請參閱 [網頁內容協助工具指南 (WCAG) 1.2.6.：手語解譯](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)。

## <a name="reduce-distractions-in-meetings"></a>減少會議干擾

開啟視訊篩選來鼓勵使用者參與，以減少 Teams 會議的干擾。

### <a name="turn-on-video-filters"></a>開啟視訊篩選

視訊篩選有助於減少會議期間的干擾。

若要開啟視訊篩選：

1. 在 Microsoft Teams 系統管理中心，移至 [ **會議]**，然後選取下拉式 **會議原則**。

2. 選取您要修改的原則。

3. 移至 **[內容共用]** 區段。

4. 在 [ **選取** 最符合貴組織合規性與安全性需求的視訊篩選] 底下選擇選項。 選取下列其中一個選項：

   - 僅背景模糊

   - 背景模糊和預設影像

   - 所有篩選

5. 選取 [儲存 **]**。

> [!TIP]
> 分享下列連結，讓使用者可以調整 Teams 會議喜好設定，以減少干擾：
> - [變更 Teams 會議中的背景效果](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)
> - [減少 Teams 會議中的背景雜音](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

### <a name="why-its-helpful-to-reduce-distractions"></a>為什麼這有助於減少干擾

由於參與者背景中的移動、光線及其他干擾，貴組織中的某些人員可能會發現很難在視訊會議和通話期間專注。 使用視訊篩選可協助使用者控制干擾並完全參與。

*背景效果* 可協助人員專注于喇叭，而非演講者的背景。 Microsoft Teams 有背景媒體櫃，使用者也可以上傳自己的背景。

*背景模糊* 有助於改善會議或通話時的可見度和專注力，因為它可以減少背景中的干擾，但能讓使用者保持專注。

視訊篩選在各種情況下都很有説明，但對下列情況特別有説明：

- 人員常用者

- 人員聽障或聽力不佳的使用者

如需詳細資訊，請參閱 [網頁內容協助工具指南 (WCAG) 1.4.8.：視覺簡報](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)。

## <a name="improve-participation-in-microsoft-teams-meetings"></a>改善 Microsoft Teams 會議的參與度

開啟 **會議中的 [聊天**]，以及聊天編輯、**沈浸式閱讀程式** 和表情圖示等訊息原則，鼓勵使用者參與，提供更多控制與彈性選項。

### <a name="turn-on-chat-in-meetings"></a>在會議中開啟聊天

聊天可讓許多使用者更輕鬆地在 Teams 會議中提出問題或新增資訊。

若要檢查會議中聊天是否已開啟：

1. 在 Microsoft Teams 系統管理中心，移至 [ **會議]**，然後選取下拉式 **會議原則**。

2. 選取您要修改的原則。

3. 移至 [ **參與者&來賓** ] 區段。

4. 選擇 [ **在會議中聊天** ] 下方的選項，以符合貴組織的合規性和安全性需求。 您可以選取下列其中一個選項：

   - 針對建議 () 的每個人開啟此功能

   - 針對不建議 () 的每個人關閉此功能

   - 針對除了匿名使用者以外的所有人開啟此功能

5. 選取 [儲存 **]**。

### <a name="use-messaging-policies-for-increased-flexibility-and-control"></a>使用訊息原則提高彈性和控制能力

彈性的聊天選項可讓許多使用者更輕鬆地瞭解其他人的訊息、修改自己的訊息，以及表達自己。

若要檢查這些彈性聊天選項是否已開啟：

在 **Microsoft Teams 系統管理中心**：

1. 在 Microsoft Teams 系統管理中心，移至 **[訊息中心原則]**。

2. 選取您要修改的原則。

3. 檢查下列專案 **是否已開** 啟：

   - **刪除已傳送的訊息**

   - **編輯已傳送的訊息**

   - **聊天**

   - **在交談中 Giphy**

   - **交談中的 Meme**

   - **交談中的圖戳**

   - **URL 預覽**

   - **翻譯訊息**

   - **訊息的沈浸式閱讀程式**

4. 選取 [儲存 **]**。

> [!TIP]
> 與貴組織分享 [如何撰寫有效替代文字](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2) 的連結，以協助使用者瞭解在聊天中共用的非文字訊息。

### <a name="why-alternate-participation-options-matter"></a>為什麼替代參與選項很重要

彈性的聊天選項可讓使用者在使用會議聊天內容的方式上擁有更大的彈性，並能更進一步控制他們參與聊天會議的方式。

*會議內聊天* 可讓人員以其他方式參與會議討論。 對某些身心障礙使用者而言，聊天可能比較適合語音或手語，做為參與會議討論的一種方式。

*沈浸式閱讀程式* 是專為閱讀障礙和閱讀障礙使用者設計的工具，可協助讓文字更容易理解。 它也包含內建翻譯，供想要以不同語言通訊的使用者使用。 沈浸式閱讀程式的一些主要功能如下：

- 新增讓內容大聲朗讀的選項

- 變更文字大小和背景色彩

- 將文字分成音節

- 增加字母之間的間距

- 醒目提示一行或多行文字

- 醒目提示詞性

彈性聊天選項在各種情況下都很有説明，但對下列情況特別有説明：

- 人員視障或弱視使用者

- 人員 (，也就是有閱讀障礙或閱讀障礙) 

如需詳細資訊，請 [參閱 WCAG (WCAG) 1.1.1.：文字替代方案](https://www.w3.org/TR/WCAG21/#text-alternatives)。

## <a name="share-resources-with-users-to-further-accessibility-awareness"></a>與使用者共用資源以進一步提高協助工具意識

使用者可以採取其他步驟來改善協助工具體驗。 與您的組織和來賓使用者共用下列連結。

### <a name="reference-links"></a>參考連結

Microsoft 身心障礙人士 Answer Desk 有使用者指南，可自訂其體驗以符合他們的協助工具需求：

- [在會議期間開啟即時輔助字幕](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)

- [自訂會議檢視](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)

- [使用 CART 標號](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

- [變更 Teams 會議中的背景效果](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)

- [減少 Teams 會議中的背景雜音](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

- [撰寫有效的替代文字](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2)

- [Microsoft Teams 的協助工具工具](https://support.microsoft.com/office/accessibility-tools-for-microsoft-teams-2d4009e7-1300-4766-87e8-7a217496c3d5?ui=en-us&rs=en-us&ad=us)

### <a name="reference-web-content-accessibility-guidelines-wcag"></a>WCAG)  (Web 內容協助工具指導方針參考

WCAG 是一系列旨在改善 Web 協助工具的國際標準。 本指南中所參照的成功準則包括：

- [WCAG 1.2.4.：標題 (即時) ](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

- [WCAG 1.2.6.：手語解譯](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)

- [WCAG 1.4.8.：視覺簡報](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)

- [WCAG 1.1.1.：文字替代方案](https://www.w3.org/TR/WCAG21/#text-alternatives)
