---
title: 在您的企業中設定 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 在您的企業中設定 Teams，讓使用者能夠使用聊天和檔案共用進行共同作業、設定與參加小型和大型會議，以及透過影片和語音進行交談。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fea59dd39023e9ac9a3234491742bc5a998926a
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395422"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>在您的企業中設定 Microsoft Teams

使用本文的資訊來引導您完成在組織中的 Teams 部署。

> [!NOTE]
> 如果您尚未部署 Teams，我們強烈建議您使用試驗版，開始您的 Teams 部署。 試驗版將允許您和一些早期採用者在規劃及真正開始使用 Teams 之前，先熟悉 Teams 及其功能。若要瞭解如何開始使用試驗版，請參閱 [開始使用 Microsoft Teams](get-started-with-teams-quick-start.md)。

在您廣泛使用 Teams 之前，請先檢閱 [確認您已準備就緒](get-started-with-teams-quick-start.md#make-sure-youre-ready) 中的項目，確認貴組織已準備就緒。

## <a name="plan-your-deployment"></a>規劃您的部署

開始部署 Teams 之前，請確定您已完成規劃程序。 您的規劃程序應包含：

- 瞭解 Teams 架構
- 檢閱及瞭解 Teams 工作負載及其與 Microsoft 365 搭配作業的方式
- 計算網路需求並確保您的網路和網際網路連接具有支援重要需求 (例如即時通訊) 所需的硬體和能力
- 瞭解儲存在 Teams 和其他 Microsoft 365 服務中的資訊之法規和合規性要求
- 建立採用計畫，協助使用者瞭解使用 Teams 的優點

我們強烈建議使用 [Teams 建議程式](https://admin.teams.microsoft.com/teams-deployment) 來協助您進行部署。 如需 Teams 建議程式運作方式的詳細資訊，請參閱 [使用 Advisor for Teams 來協助您開始使用 Microsoft Teams](use-advisor-teams-roll-out.md)。

> [!TIP]
> 完成 Microsoft Learn 上的 [使用 Teams 建議程式以開始使用](https://docs.microsoft.com/learn/modules/m365-teams-rollout-using-advisor/) 模組，以瞭解如何使用 Teams 建議程式來協助您規劃 Teams 部署。

如需規劃 Teams 的詳細資訊，請參閱 [Teams 企業部署概觀](deploy-enterprise-overview.md)。

## <a name="workloads"></a>工作負載

有許多方法可以自訂 Teams。 下列各章節將說明如何設定每個 Teams 工作負載：**聊天、團隊和頻道**；**會議與召集會議**；和 **電話系統**。 您對每個工作負載的順序設定由您決定。 雖然我們建議您先設定聊天、團隊和頻道工作負載，但您也可以從會議和召集會議，甚至是電話系統開始設定。

#### <a name="chat-teams-and-channels"></a>[聊天、團隊和頻道](#tab/ChatTeamsChannels)

聊天、團隊和頻道是 Teams 的基礎。 **聊天** 可讓一或多個使用者彼此交談、共用檔案，以及私下開會。 **團隊**，(可選擇允許貴組織所有人或只有團隊中的人員可以看到) 可讓適當的人員無論工作或場合為何、無論是長時間作業的專案或是規劃生日派對，皆能共同作業。 團隊中的 **頻道** 可以區隔主題、專案、部門或其他任何對您的團隊有意義的項目。 如需聊天、團隊和頻道的詳細資訊，請參閱 [團隊和頻道概觀](teams-channels-overview.md)。

> [!TIP]
> 在 Microsoft Learn 上完成 [管理 Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-teams/) 模組，以瞭解如何管理團隊角色、存取權限與訊息傳遞原則。

### <a name="administration-and-team-ownership"></a>系統管理和團隊擁有權

| 決策 | 描述 |
|--|--|
| 誰應該當 Teams 系統管理員？ | 系統管理員角色可用以將特定權限授予您希望負責管理 Teams 的人。 小型企業可能不需要這些額外的角色，因為同一個人可能需負責 Teams 的各個層面。 稍後您隨時都可以新增或移除系統管理員。<p>[使用 Microsoft Teams 系統管理員角色來管理 Teams](using-admin-roles.md) |
| 誰應該當 Teams 擁有者與誰應該當成員？ | 團隊擁有者可控制誰可以存取團隊及其頻道。 他們可以決定團隊或頻道是 (對組織) 公開，或私人，也可以設定原則 (如頻道是否應該受到管理)。 成員可以存取團隊及其頻道 (除非該頻道設為私人頻道，且該成員並非此頻道的成員)，而且可以被指定為仲裁者。<p>[在 Microsoft Teams 中指派 Teams 擁有者和成員](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>預設設定和生命週期原則

| 決策 | 描述 |
|--|--|
| 應套用哪些訊息傳遞原則？ | 訊息傳迪原則可控制哪些聊天和頻道傳訊功能 (例如誰可以使用聊天、誰可以編輯及刪除已傳送的訊息等等) 可供 Teams 使用者使用。 Teams 具有適用於所有人的全域原則。 全域原則中的所有功能依預設為 **開啟**。<p>如果您想要將相同的原則套用于所有人，您只需要變更此全域原則 (例如，關閉交談中的 Meme 支援)。<p>如果您想要將不同的原則套用于不同的人員群組 (例如，將一個原則套用于辦公室員工，另一個原則套用于工廠員工)，您可以建立並指派原則。 當您將原則指派給使用者時，他們將不再適用全域原則。<p>[管理 Teams 中的訊息傳遞原則](messaging-policies-in-teams.md) |
| 應套用哪些 Teams 設定？ | Teams 設定可讓您為團隊設定使用電子郵件整合、雲端儲存選項、組織索引標籤、會議室裝置設定和搜尋範圍等功能。 對這些設定進行變更時，設定會套用到組織中的所有團隊。 <p>[Teams 設定](enable-features-office-365#teams-settings)  |

### <a name="external-and-guest-access"></a>外部和來賓存取

| 決策 | 描述 |
|--|--|
| 應啟用外部存取嗎？ | 外部存取可讓另一個組織的任何人與貴組織的人交談。 當您與另一個組織 (例如供應商) 有密切關係，並且想要讓任一組織的人能輕鬆地彼此聊天、開會等等時，這非常有用。 <p>外部存取與來賓存取不同。 外部存取讓另一個組織的每個人都能夠與貴組織的人員進行互動。 來賓存取會邀請特定人員存取與貴組織人員的互動。<p>外部存取依預設為 **關閉**。<p>[在 Microsoft Teams 中管理外部存取](manage-external-access.md)  |
| 應啟用來賓存取嗎？ |來賓存取可讓貴組織的人員邀請貴組織外的人員存取貴團隊和頻道。 來賓存取通常用於與貴組織外部且與貴組織人員沒有正式關係的人員進行共同合作。 例如，您可以邀請專案規劃人員暫時進行某一專案。<p>來賓存取與外部存取不同。 來賓存取會邀請特定人員存取與貴組織人員的互動。 外部存取讓另一個組織的每個人都能夠與貴組織的人員進行互動。 <p>來賓存取依預設為 **關閉**。 <p>[開啟或關閉 Microsoft Teams 的來賓存取](set-up-guests.md)  |

#### <a name="meetings-and-audio-conferencing"></a>[會議和音訊會議](#tab/MeetingsAudioConferencing)

會議和召集會議可讓貴組織的人員彼此以及與組織外部的人員開會。 擁有 Teams 或商務用 Skype 用戶端的任何人都可以受邀加入 **會議**。 使用裝置中的麥克風、相機和螢幕可讓參與者無需使用電話便能加入交談。 參與者可以使用電腦或行動裝置與其他參與者聊天、進行語音通話，以及分享影片和應用程式。

**音訊會議** 可讓參與者透過撥打會議電話號碼並輸入會議識別碼使用一般電話來加入會議。 當參與者沒有良好的網路連線、會議為僅供語音使用，或某些不允許參與者透過 Teams 用戶端加入會議的情況時，音訊會議便非常有用。

> [!TIP]
> 完成 Microsoft Learn 上的 [使用 Microsoft Teams 來管理會議、召集會議與活動](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-meetings) 模組，以更加熟悉會議與活動。

### <a name="meetings"></a>會議

| 決策 | 描述 |
|--|--|
| 應套用哪些全組織會議設定| 會議原則控制哪些會議功能可供會議召集人和參與者使用。 您可以控制匿名參與者是否可以加入會議、自訂會議邀請、控制即時媒體的處理方式等等。 當您對這些設定進行變更時，設定會套用到貴組織中的所有會議。 <p>[在 Microsoft Teams 中管理會議設定](meeting-settings-in-teams.md)|
| 應套用哪些會議原則？ | 會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。 您可以控制使用者是否可以排程私人會議、啟用 [現在開會] 選項、允許錄製會議等等。 Teams 具有適用於所有人的全域原則。<p> 如果您想要將相同的原則套用于所有人，您只需要變更此全域原則 (例如，關閉會議錄製功能)。 <p>如果您想要將不同的原則套用于不同的人員群組 (例如，將一個原則套用于辦公室員工，另一個原則套用于主管)，您可以建立並指派原則。 當您將原則指派給使用者時，他們將不再適用全域原則。<p> [管理 Teams 中的會議原則](meeting-policies-in-teams.md)|
| 是否要允許會議錄製及封存？| 會議召集人可以在雲端中錄製及封存會議。 您可以使用會議原則開啟或關閉會議錄製和封存功能。<p> [Teams 雲端會議錄製](cloud-recording.md) |

### <a name="audio-conferencing"></a>音訊會議

| 決策 | 描述 |
|--|--|
| 是否要設定與協力廠商解決方案的視訊交互操作性？| 雲端視訊交互操作性可讓協力廠商遙現和個人視訊裝置加入 Teams 會議。 如果您已經投資於視訊會議和個人視訊裝置，您可以使用視訊交互操作性將這些裝置與 Teams 相整合。<p> [Microsoft Teams 雲端視訊 Interop](cloud-video-interop.md)。|
| 應套用哪些全組織音訊會議設定？| 音訊會議設定可讓您控制會議參與者使用電話撥打加入會議的方式。 您可以設定加入會議所需的 PIN 長度、重設會議識別碼、啟用或停用傳送音訊會議資訊給參與者等等。 音訊會議設定變更適用于貴組織的每個人。<p>[在 Microsoft Teams 管理貴組織的音訊會議設定](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) |
| 會議召集人是否需要撥出通話至任何目的地？| 從音訊會議撥打到貴組織外的電話號碼時，會使用 [通訊點數]。 您必須購買足夠的 [通訊點數]，以確保音訊會議通話期間點數不會用完。<p>部分音訊會議訂閱可能包含撥出通話。 請查看您的訂閱資訊以瞭解詳細資訊。<p> [設定貴組織的 [通訊點數]](set-up-communications-credits-for-your-organization.md)|
| 應套用哪些撥出通話限制？| 您可以使用撥出通話控制來限制組織中的使用者可進行的音訊會議類型通話類型。 例如，您可以控制會議是否可以撥打國際電話號碼、撥打任何撥出電話、僅限撥打特定國家/地區等等。<p>[音訊會議和使用者 PSTN 通話的撥出通話限制原則](outbound-calling-restriction-policies.md) |
| 是否要變更 Teams 轉譯撥打電話號碼的方式？ | 您可以使用撥號對應表控制轉譯電話號碼的方式。 例如，您可以設定要撥打哪一個號碼以聯繫外線電話、控制電話分機的處理方式、設定首碼，讓撥打的分機轉譯為完整電話號碼等等。<p> [建立和管理撥號對應表](create-and-manage-dial-plans.md) |
| 是否要啟用即時活動？ | 即時活動能讓您對大型觀眾進行影片和會議內容直播。 如果您啟用即時活動，您就可以為其設定原則，以控制其使用方式。 例如，您可以設定 URL 參與者應用於支援、設定協力廠商視訊分配提供者 (如果您有的話) 等等。 Teams 具有適用於所有人的全域原則。<p>如果您想要將相同的原則套用于所有人，您只需要變更此全域原則。 <p>如果您想要將不同的原則套用于不同的人員群組 (例如，將一個原則套用于辦公室員工，另一個原則套用于主管)，您可以建立並指派原則。 當您將原則指派給使用者時，他們將不再適用全域原則。<p> [在 Microsoft Teams 中設定即時活動](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[電話系統與 PSTN 連線](#tab/PhoneSystem)

[電話系統] 可讓您以 Microsoft 365 提供的一系列緊密整合至雲端體驗的功能取代現有的內部部署電話系統。

| 決策 | 描述 |
|--|--|
| 是否要取代您的內部部署電話系統？ | 設定 [電話系統]、設定自動語音應答、通話方案、通話佇列等等。 <p> [設定貴組織的 [電話系統]](setting-up-your-phone-system.md)|
| 是否要設定 [雲端語音信箱] 原則？| 您可以控制哪些 [雲端語音信箱] 功能可供使用者使用，以及這些功能如何運作。 例如，您可以為整個組織啟用或停用語音信箱謄寫功能、啟用或停用特定使用者的猥褻遮蔽功能等等。<p> [設定 [雲端語音信箱]](set-up-phone-system-voicemail.md) |
| 是否要啟用動態緊急電話？| 動態緊急電話可讓您根據網路設定及其他中繼資料來設定位置地圖，以判斷當使用者撥打緊急電話時需派遣緊急人員的位置。 您可以設定網路設定、將緊急位址指派至位置等等。<p>[規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md) |
| 是否要自訂來電顯示行為？ | 根據預設，Teams 使用者進行通話時所顯示的電話號碼就是使用者的電話號碼。 您可以將此變更為公司的主要號碼、封鎖電話號碼、將號碼匿名或顯示為其他服務號碼。 Teams 具有適用於所有人的全域原則。<p>如果您想要將相同的原則套用于所有人，您只需要變更此全域原則。 <p>如果您想要將不同的原則套用于不同的人員群組 (例如，將一個原則套用于辦公室員工，另一個原則套用于主管)，您可以建立並指派原則。 當您將原則指派給使用者時，他們將不再適用全域原則。<p> [管理 Microsoft Teams 中的來電顯示原則](caller-id-policies.md)。 |

---

## <a name="security"></a>安全性

Teams 的設計與開發符合 [Microsoft 高可信度電腦運算安全性開發週期 (SDL)](https://www.microsoft.com/sdl/default.aspx) 的規範。 為了符合 SDL，Teams 將業界標準安全性技術納入其架構的基礎部分中，包括：

- 設計威脅模型，然後針對這些功能進行測試
- 將安全性相關的改進納入程式碼撰寫和慣例中
- 在程式碼移轉至產品之前，建立建置階段工具以偵測緩衝區溢位和其他潛在的安全性威脅

雖然 Teams 遵循「可信性設計」方法，但無法針對所有未知的安全性威脅進行設計。 因此，瞭解 Teams 的運作及其與其他系統之互動方式非常重要。 瞭解常見威脅 (例如 IP 位址詐騙、拒絕服務攻擊、中間人攻擊等) 的運作方式也非常重要，這樣您才能設計您的網路和 Teams 配置，以降低發生這些攻擊的機會。

若要瞭解 Teams 如何將安全性基礎納入其設計之中，以及閱讀更多有關常見威脅的深入資訊，請參閱 [安全性與 Microsoft Teams](teams-security-guide.md)。

## <a name="compliance"></a>合規性

Teams 和 Microsoft 365 提供許多工具，協助符合貴公司和使用者所在地的法規要求。 請參閱下列文章，以瞭解如何設定 Teams 中的每個合規性功能：

| 功能 | 描述|
|-|-|
| [資訊屏障](information-barriers-in-teams.md)| 防止個人或群組彼此通訊，或在使用者選擇器中彼此尋找。|
| [保留原則](retention-policies.md)| 可讓您控制 Teams 中的資料應保留多久，或在特定時間之後是否必須移除資料。|
| [通訊合規性](communication-compliance.md)| 透過識別冒犯性、褻瀆性及騷擾性語言；成人色情內容、血腥影像；以及敏感性資訊的分享，並對此採取行動，以協助降低通訊風險。 |
| [通話和會議的原則式錄製](teams-recording-policy.md)| 可讓您控制何時或是否要自動錄製並儲存通話和會議，供日後處理、保留或分析。|
| [敏感度標籤](sensitivity-labels.md)| 建立強制執行所選隱私權選項的標籤，協助您保護及規範敏感性資訊的存取。|
| [資料遺失防護](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?toc=%2Fmicrosoftteams%2Ftoc.json&bc=%2Fmicrosoftteams%2Fbreadcrumb%2Ftoc.json&view=o365-worldwide)| 可讓您建立規則，決定如何處理特定資訊 (例如社會安全號碼、信用卡號碼等等)。 您可以防止特定資訊的傳送、避免該資訊自貴組織流出等等。|
| [電子文件探索](eDiscovery-investigation.md)| 當貴組織在法律程序中收到資訊探索要求時，可協助您搜尋並檢索貴組織中的內容。 |
| [法務保存措施](legal-hold.md)| 可協助您將資訊保留在貴組織中 (即使該資訊已遭使用者刪除)，則若法律程序期間需要該文件，便可在電子文件探索調查過程中找到。 |
| [內容搜尋](content-search.md)| 提供跨 Exchange、SharePoint Online 和商務用 OneDrive 查詢 Teams 資訊的方法。|
| [稽核](audit-log-events.md)| 可讓您查看指定動作的資訊，包括動作執行者、執行動作時間、使用的 IP 位址等等。 動作包括在 Teams 中建立或刪除團隊、建立頻道、變更設定等等。|
| [客戶金鑰](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level?toc=%2Fmicrosoftteams%2Ftoc.json&bc=%2Fmicrosoftteams%2Fbreadcrumb%2Ftoc.json&view=o365-worldwide)| 可讓您使用您提供的加密金鑰來建立資料加密原則。|

## <a name="clients"></a>用戶端

當您準備好讓使用者開始使用 Teams 時，他們可以在其 Windows、Mac 或 Linux 電腦或其 Android 或 iOS 裝置上安裝 Teams 用戶端。 使用者可以直接從 <https://teams.microsoft.com/downloads>下載 Teams 用戶端。

請確定所有將使用 Teams 的人都具有 Teams 授權。 如需指派 Teams 授權的詳細資訊，請參閱 [管理使用者對 Teams 的存取權](user-access.md#using-the-microsoft-365-admin-center)。

> [!TIP]
> 完成 Microsoft Learn 上的 [部署 Microsoft Teams 用戶端](https://docs.microsoft.com/learn/modules/m365-teams-collab-deploy-clients/) 模組，以取得規劃 Teams 用戶端部署的建議。

如果貴組織使用 Microsoft Endpoint Configuration Manager、群組原則或協力廠商分配機制，將軟體部署到使用者的電腦上，請參閱 [使用 Microsoft Endpoint Configuration Manager 來安裝 Microsoft Teams](msi-deployment.md)。

如果您想要部署 Teams 用戶端的詳細資訊，請參閱 [取得 Microsoft Teams 用戶端](get-clients.md)。

## <a name="training"></a>訓練課程

若要瞭解如何訓練使用者和系統管理員使用 Teams，請參閱 [Microsoft Teams 訓練課程](training-microsoft-teams-landing-page.md)。
