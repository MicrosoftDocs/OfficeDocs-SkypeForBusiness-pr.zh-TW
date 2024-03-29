---
title: 音訊會議免付費電話號碼原則
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: 瞭解 Microsoft 365 或 Office 365 中的音訊會議如何允許使用者從其電話撥入會議。
ms.openlocfilehash: 8fcc731f208dc3fecd42dd2c351714f67ad6a684
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732402"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>付費和免付費電話號碼的音訊會議原則設定

## <a name="teams-audio-conferencing-policy"></a>Teams 音訊會議原則

使用音訊會議原則來管理由組織內使用者建立的會議邀請所顯示的音訊會議付費和免付費電話號碼。 您可以使用兩個自動建立的原則之一，或建立及指派自訂原則。 自動建立的兩個原則是全全組織 (預設) ，以及 AllowTollFreeDialinFalse (指派給組織中所有未啟用免付費撥入號碼) 的現有使用者。 您可以在 Microsoft Teams 系統管理中心或使用 [PowerShell](teams-powershell-overview.md)管理音訊會議原則。

- AllowTollFreeDialin 的設定無法再透過 Teams 系統管理中心或 PowerShell 管理個別使用者。 租使用者系統管理員只能透過新的音訊會議原則來管理此設定。
- 無法從 Teams 系統管理中心修改全域原則。

> [!NOTE]
> 客戶不支援自訂音訊會議原則，商務用 Skype地區託管會議。 啟用地區託管會議的客戶可以透過預設設定來管理使用者的音訊會議設定。 您可以在 Teams 管理員 中心流覽至 [使用者 **管理**  ->  使用者] 選取 [**使用者**  ->  帳戶]，變更 **使用者**  ->  的音訊會議預設 **設定**。

在租使用者中啟用 Teams 音訊會議原則時，租使用者中會自動建立兩個可用的原則。 這兩個原則會自動建立，其預設設定如下：

### <a name="global-org-wide-default"></a>全域 (組織的預設) 

在此原則中， **AllowTollfreedialin** 的值將會設定為 [開啟]，且原則中不會定義任何電話號碼。 對於啟動時將 **AllowTollfreedialin** 設為 [開啟] 之租使用者中的所有使用者，這將會是預設 **原則。**
由於原則並未定義任何電話號碼，因此當此原則的使用者建立 Teams 會議時，其會議中可用的電話號碼會與該原則之前使用者擁有的電話號碼相同。 除非租使用者系統管理員變更個別使用者的電話號碼，否則這些電話號碼通常預設為使用者的國家/地區/位置。

例如，如果德國以外的使用者在啟動音訊會議原則之前指派了德國的付費電話號碼和免付費電話號碼，那麼在啟動時，使用者會獲得全域原則的指派，而他們會在會議邀請中繼續看到的電話號碼，與套用原則之前一樣 (也就是說， 德國的付費電話號碼和免付費電話號碼) 。 啟動原則時，使用者不會看到任何變更。 不過，如果租使用者系統管理員修改了全域原則，並在原則中包含與之前不同的特定電話號碼，則原則的所有使用者將只會看到原則中包含在他們所排程的任何會議中的電話號碼。

> [!NOTE]
> 如果租使用者管理員沒有修改全域原則，而是建立自訂原則並將它套用至使用者，那麼自訂原則中定義的設定將會是使用者在會議邀請中看到的內容。

例如，如果自訂原則有「AllowTollFreeDialinFalse」且未定義電話號碼，則此原則的使用者將無法擁有免付費電話號碼，而且原則中不會定義任何電話號碼，因此，由這類使用者建立的會議邀請所用的付費電話號碼會與該原則之前使用者的電話號碼相同。 除非租使用者系統管理員變更個別使用者的電話號碼，否則這些電話號碼通常預設為使用者的國家/地區/位置。

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

在此原則中， **AllowTollfreedialin** 的值會設為 **[關閉** ]，且原則中不會定義任何電話號碼。 對於在啟動時將 **AllowTollfreedialin** 設為 [ **關閉**] 之租使用者中的所有使用者，此為預設原則。

由於原則並未定義任何電話號碼，因此當此原則的使用者建立小組會議時，可在其會議中取得的電話號碼會與使用者在原則之前擁有的電話號碼相同。 除非租使用者系統管理員針對個別使用者變更此設定，否則這些電話號碼通常預設為使用者的國家/地區或位置。

例如，如果德國以外的使用者在啟動音訊會議原則之前，已經指派了德國付費電話號碼，那麼在啟動時，使用者會被指派「AllowTollfreedialinFalse」原則，而他們會在會議邀請中繼續看到的電話號碼會和之前一樣 (也就是說， 德國的付費電話號碼) 。 啟動原則時，使用者不會看到任何變更。 不過，如果租使用者系統管理員修改 **了 AllowTollfreedialinFalse** 原則，並將特定電話號碼包含在原則中，則所有原則使用者只會看到原則中包含在他們排程的任何會議中的電話號碼。

## <a name="create-a-custom-audio-conferencing-policy"></a>建立自訂音訊會議原則

步驟概觀：

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至會議>音訊會議。
1. 選取 [新增]。
1. 輸入原則的名稱和描述。 名稱不能包含特殊字元，且長度不可超過 64 個字元。
1. 選擇您想要的設定。
1. 選取 [儲存]。

例如，您可能有一組使用者定期與來自多個國家/地區的參與者開會。 在我們的範例中，參與者來自加拿大、波劄那和新加坡，而且都想要透過音訊會議撥打電話號碼加入會議。 您可以建立名為「加拿大波劄那新加坡」的新自訂原則，並透過 [ **新增電話號碼** ] 選項選取這三個國家/地區的電話號碼，並儲存此原則。 接著，您可以將此原則指派給必要的使用者。

這可確保您針對加拿大、波劄那及新加坡選取的電話號碼會包含在這項原則使用者所建立的會議邀請中。

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>根據範例建立自訂原則的逐步指示

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[會議**  >  **音訊會議]**。
2. 選取 [新增 **]**。
3. 輸入原則的名稱和描述。 名稱不能包含特殊字元，且長度不可超過 64 個字元。
4. 選擇是否要在由此原則使用者建立的會議中包含免付費電話號碼。 將此設定設為 **[開啟** ] 可讓您在此原則中新增免付費電話號碼。
5. 選取 [新增電話號碼]。
6. 畫面右側會開啟一個窗格，其中包含 [依 **位置搜尋] 方** 塊。
7. 輸入加拿大，然後從結果中選取來自加拿大的電話號碼。
8. 選取 [新增 **]**。
9. 重複步驟 6 和 7，以同樣的方式搜尋及新增來自波劄那和新加坡的電話號碼。
10. 如果您已開啟這個原則的使用者在步驟 4 中 **建立的會議中包含免付費電話號碼** 的設定，請選取免付費電話號碼。
11. 選取窗格右下角的 [ **新增** ]。 系統會列出您所選取之三個國家/地區的電話號碼。
12. 有一個排名欄可決定電話號碼在由此原則使用者建立的會議邀請中顯示的順序。 您可以分別使用 **[上** 移] 和 [下移] 按鈕，選取電話號碼並將它向上或 **向下** 移動，藉此變更順序。
13. 將電話號碼依喜好設定順序排列之後，請選取 [ **儲存]**。
14. 您的自訂原則「加拿大波劄那新加坡」已建立。
15. 建立完成後，您可以將此原則指派給使用者。

## <a name="edit-a-meeting-policy"></a>編輯會議原則

您可以編輯您建立的任何自訂原則。  (請注意，無法從 Teams 系統管理中心編輯全域原則) 

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[會議**  >  **音訊會議]**。
1. 選取原則名稱左側，然後選取 [ **編輯**]，選擇您要編輯的原則。
1. 進行編輯。
1. 選取 [儲存 **]**。

> [!NOTE]
> 如果已將原則指派給使用者，就無法刪除該原則。 您必須將不同的原則指派給所有受影響的使用者，然後才能刪除原始原則。

## <a name="assign-a-meeting-policy-to-users"></a>將會議原則指派給使用者

> [!IMPORTANT]
> 套用新的音訊會議原則給使用者後，原則中定義的電話號碼就只能在使用者使用此原則建立的新會議中使用。 任何在原則之前排程的舊和週期性會議都會繼續顯示舊的設定，例如，如果已為該使用者啟用免付費電話， (一個付費電話號碼) 。 這裡的案例可能是使用者已開啟 **[允許免付費** ]，並已指派免付費電話號碼，且他們已針對未來建立週期性會議。 在此案例中，如果您使用 AllowTollfreeDialIn **關閉** 建立自訂原則並將它套用到此使用者，此使用者建立的任何新會議將不會包含免付費電話號碼，但舊的週期性會議仍會顯示免付費電話號碼。 因此，如果來電者撥打這個免付費電話號碼加入會議，電話將會失敗，因為這個使用者現在已因原則而停用免付費電話。 若要避免這種情況，您可以在指派新的音訊會議原則之後，移轉使用者的舊會議。 請檢閱 [使用會議移轉服務 (MMS) ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。

如果原則類型) 支援，您可以直接將原則指派給使用者或使用者為 (成員的群組，如果支援該原則類型) ，您可以透過批次處理工作分派個別或大量指派 (。

若要瞭解您可以指派原則給使用者的不同方式，請參閱 [指派原則給使用者和群組](assign-policies-users-and-groups.md)。

> [!NOTE]
> 使用者一次只能指派一個音訊會議原則。

> [!IMPORTANT]
> 指派的電話號碼最多可能需要 24 小時，才會顯示在您的會議邀請上。 如果您沒有看到更新號碼出現，請等候至少 24 小時，然後再連絡支援服務。

### <a name="known-issue"></a>已知問題

當您使用 Microsoft Teams 的 [ **立即開會** ] 選項開始會議時，>行事曆>認識 Mow，如果您接著選取省略號...功能表選項，然後 [會議資訊] 下方區段的下半部會發生問題， **或僅 () 的音訊通話**。 系統會顯示原則中定義的所有電話號碼，但號碼的對齊方式會讓您難以閱讀。
