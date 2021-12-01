---
title: 設定接線連線會議
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解如何設定運算子連線會議。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257506"
---
# <a name="configure-operator-connect-conferencing"></a>設定接線連線會議

本文詳細說明如何為貴連線使用者設定運算子和會議。

在將運算子連線會議之前，請參閱接線連線[會議](operator-connect-conferencing-plan.md)方案，以瞭解權益和授權需求的資訊。

本文涵蓋的主題包括：

- [設定運算子](#set-up-an-operator)
- [取得音訊會議橋接器的號碼](#acquire-numbers-for-your-audio-conferencing-bridge)
- [變更使用者會議邀請中包含的預設電話號碼](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [透過接線Microsoft Teams從會議傳送外寄電話](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [管理運算子](#manage-your-operators)
- [音訊會議橋接器的發行號碼](#release-numbers-from-your-audio-conferencing-bridge)
- [管理 Microsoft 音訊會議的其他資訊](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>設定運算子

您可以在系統管理中心設定、編輯及移除Teams運算子。 在左側流覽窗格中，前往語音> **運算子**。

若要設定運算子：

1. **選擇運算子。**  在 " **所有運算子"** 的 Tab 中，根據地區或服務篩選可用的運算子，以尋找適合您   語音需求的運算子。 然後，選取您想要使用的運算子。 針對接線連線會議，請確認您的接線員已將 **會議列為** 可用產品。

2. **選取國家/地區。**  在  **運算子設定** 下，選取您想要使用所選運算子啟用的國家/地區。

3. **提供連絡人資訊**  您的連絡人資訊 ，包括您的全名和電子郵件地址，將會與您的接線員共用。 您可以稍後變更這項資訊。 此外，您必須提供公司規模，並提供提供電話號碼的選項。 運算子會使用這項資訊來與您聯繫，以進一步連線會議。

4. 接受資料傳輸通知。

5. **新增運算子。**  選取  **新增為運算子**   以儲存。

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>取得音訊會議橋接器的號碼

貴組織的音訊會議橋接器包含組織中所有使用者都可以使用的電話號碼，Microsoft Teams PSTN 電話號碼加入會議。 您可以在會議橋接器下的系統管理中心Teams與貴組織音訊會議橋接器>**電話號碼**。

若要取得音訊會議橋接器的電話號碼，請遵循下列步驟：

1. **音訊會議標準訂閱或運算子連線會議授權。** 需要接線連線號碼才能加入他們組織的會議的使用者，必須擁有音訊會議標準訂閱授權，或指派連線電話機授權給他們。 詳細資訊，請參閱規劃接線[連線會議](operator-connect-conferencing-plan.md)。

2. **取得數位。**  請前往您的接線員網站訂購並取得電話號碼。 若要查看運算子網站清單，請前往 Microsoft 365 [運算子連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱尋找您的租[使用者](/onedrive/find-your-office-365-tenant-id)識別碼Microsoft 365識別碼。 您的運算子完成訂單後，就會將號碼上傳至您的租使用者。 您可以在系統管理中心查看號碼Teams提供者，> 電話 **號碼**。

3. **將號碼指派給音訊會議橋接器。** 您可以在會議橋接器和新增 會議橋接器下，從 Teams 系統管理中心將>**號碼>橋接器**。 詳細資訊，請參閱 [變更音訊會議橋接器上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

>[!NOTE]
>您無法將接線連線號碼指派為橋接器的預設號碼。 將電話號碼指派給音訊會議橋接器後，號碼會列在組織中具有音訊會議授權或運算子 連線會議授權之會議邀請中包含的當地號碼頁面。
>
>若要透過接線員路由外寄電話，[**請參閱**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)本文進一步Teams透過接線員傳送來自會議外寄電話一節。

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>變更使用者會議邀請中包含的預設電話號碼

 此步驟為選擇性。

使用者的預設電話號碼是排程會議時包含在會議邀請中的號碼。 您可以更新使用者管理中心中使用者會議邀請Teams使用者>**電話號碼**。 若要更新使用者會議邀請中包含的電話號碼，請選取使用者，然後選取音訊 **會議區段** 的編輯。

變更已採用之後，召集人的新會議邀請會包含新的預設電話號碼。 不過，變更之前排定的現有會議邀請會保留原始的預設號碼。

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>透過接線Microsoft Teams從會議傳送外寄電話

如果您有 Microsoft 音訊會議標準訂閱或運算子 連線 會議授權，您可以設定音訊會議服務，透過您的接線員路由所有或一組來自 Teams 會議的外發通話，方法為設定音訊會議路由策略。

>[!NOTE]
>使用運算子連線會議授權，外線通話只能透過您的接線員。 如果您有接線連線會議授權，您必須如下列所述設定服務，才能從會議Teams電話號碼進行外撥。

您可以在使用者層級上適用音訊會議路由原則，也就是說，您的接線員只會路由來自具有關聯原則Teams使用者所組織之會議外接的來電。 您也可以在全域層級上適用這些原則，也就是說，您的接線員會從貴組織中所有使用者Teams會議路由出站通話。

使用 PowerShell，建立貴組織的新音訊會議路由策略。 若要指定運算子做為從會議Teams外通話的主要路由，請按照下列步驟使用指示的 PowerShell 命令：

1. [步驟 1：新增字串至線上 PSTN 使用政策](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [步驟 2：建立新的線上語音路由策略](#step-2-create-a-new-online-voice-route-policy)
3. [步驟 3：建立新的線上音訊會議路由策略](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [步驟 4：指派新策略給使用者](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>步驟 1：新增字串至線上 PSTN 使用政策

請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) 以進一瞭解更多關於使用此 Cmdlet 的資訊。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>步驟 2：建立新的線上語音路由策略

請參閱 [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) 以進一瞭解更多關於使用此 Cmdlet 的資訊。

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>步驟 3：建立新的線上音訊會議路由策略

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>步驟 4：指派新策略給使用者

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>若要將音訊會議路由原則設定為全域，並套用至貴組織的所有使用者，您可以使用參數 ``-Global`` 而非 ``-Identity`` 參數。 例如 ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` ，。

當您建立音訊會議路由原則並適用于使用者時，提供參數中指定電話號碼的接線Teams路由到 ``BridgeSourcePhoneNumber`` PSTN 電話號碼。 此外，參數會指定要用於 PSTN 電話號碼之外接電話之電話線識別 ``BridgeSourcePhoneNumber`` 電話號碼的電話號碼。

在 中指定的模式為 RegEx 表單，並指定要路由到您的運算子 ``NumberPattern`` 的通話。 上述 ``"\d+"`` 範例中的模式符合來自會議的所有Teams通話。 您也可以將 NumberPattern 參數設定為 ，以下列格式比對撥號號碼  ``“^\+1(425|206)(\d{7})$”`` ：+1 425 XXX XX XX 或 +1 206 XXX XX XX，或與下列格式的撥號號碼比對 ``“^\+1(\d{10})$”`` ：+1 425 XXX XX XX。

將音訊會議路由策略指派給使用者後，其會議的所有通話都指派給符合其音訊會議路由策略路由中指定之 RegEx 的電話號碼，包括透過邀請某人或撥打號碼會議選項所啟動的通話和通話撥打電話給我。 

## <a name="manage-your-operators"></a>管理運算子

在 " **我的運算子"** 選項卡中，您可以   查看運算子及其狀態，並變更下列選取專案：

- 根據國家/地區管理運算子服務
- 暫停運算子
- 移除運算子

>[!NOTE]
>從組織或國家/地區移除接線員之前，您必須移除指派給使用者和音訊會議橋接器的所有電話號碼，然後與接線員聯繫以放開號碼。

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>音訊會議橋接器的發行號碼

若要從 Teams 系統管理中心從音訊會議橋接器釋出電話號碼，請參閱在變更音訊會議橋接器上的電話號碼中取消為會議橋接器未指定服務電話號碼時[的步驟。](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>管理 Microsoft 音訊會議的其他資訊

若要進一步瞭解如何管理貴組織的 Microsoft 音訊會議，請參閱下列文章：

- 管理貴組織的 Microsoft 音訊會議服務設定：[在](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)Microsoft Teams

- 管理貴組織中使用者的 Microsoft 音訊會議服務設定：管理組織中使用者的音訊會議[Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 變更音訊會議電話號碼的自動語音語音處理語言：[設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)音訊會議中的自動語音Microsoft Teams
