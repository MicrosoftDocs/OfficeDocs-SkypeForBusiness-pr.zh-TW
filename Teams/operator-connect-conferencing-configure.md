---
title: 設定電信業者連線會議
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
description: 深入瞭解如何設定電信業者連線會議。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ade65551ad30c15fd209aa542781edce44bd76dd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676025"
---
# <a name="configure-operator-connect-conferencing"></a>設定電信業者連線會議

本文詳細說明如何為您的組織和使用者設定電信業者連線會議。

設定電信業者連線會議之前，請參閱[規劃電信業者連線會議](operator-connect-conferencing-plan.md)，以取得權益和授權需求的相關資訊。

本文涵蓋的主題包括：

- [設定運算子](#set-up-an-operator)
- [取得音訊會議橋接器的數位](#acquire-numbers-for-your-audio-conferencing-bridge)
- [變更使用者會議邀請中包含的預設電話號碼](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [透過電信業者從Microsoft Teams會議傳送撥出電話](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [管理您的運算子](#manage-your-operators)
- [音訊會議橋接器的版本號碼](#release-numbers-from-your-audio-conferencing-bridge)
- [管理 Microsoft 音訊會議 的其他資訊](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>設定運算子

您可以在系統管理中心設定、編輯及移除Teams運算子。 在左側功能窗格中，移至 **[語音>運算子]**。

若要設定運算子：

1. **選擇運算子。** 在 [ **所有運算子]** 索引標籤中，依地區或服務篩選可用的運算子，以尋找適合您語音需求的運算子。 然後，選取您要使用的運算子。 針對電信業者連線會議，請確認您的電信業者已將 **會議** 列為可用產品。

2. **選取 [國家/地區]。** 在 [ **運算子設定] 底** 下，選取您要使用所選運算子啟用的國家/地區。

3. **提供連絡資訊** 您的連絡資訊，包括您的全名和電子郵件地址，將會與您的電信業者共用。 您可以稍後變更這項資訊。 此外，您必須提供公司規模，以及提供電話號碼的選項。 運算子會使用此資訊與您連絡，以取得有關電信業者連線會議的詳細資料。

4. 接受資料傳輸通知。

5. **新增您的運算子。** 選 **取 [新增為我的運算子** ] 以儲存。

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>取得音訊會議橋接器的數位

貴組織的音訊會議橋接器包含可讓貴組織中所有使用者使用 PSTN 電話號碼加入Microsoft Teams會議的電話號碼。 您可以在會議>會議橋底下的Teams 管理員中心，看到與貴組織音訊會議 **橋接器** 相關聯的電話號碼。

若要取得網音訊會議橋接器的電話號碼，請遵循下列步驟：

1. **音訊會議標準訂閱或電信業者連線會議授權。** 需要電信業者連線會議號碼才能加入其組織會議的使用者，必須擁有音訊會議標準訂閱授權或指派電信業者連線會議授權。 如需詳細資訊，請參閱[規劃電信業者連線會議](operator-connect-conferencing-plan.md)。

2. **取得數位。** 移至您電信業者的網站以訂購及取得電話號碼。 如需電信業者網站清單，請移至[Microsoft 365 電信業者連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供您的租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱[尋找您的Microsoft 365租使用者識別碼](/onedrive/find-your-office-365-tenant-id)。 您的電信業者完成訂單後，就會將號碼上傳至您的租使用者。 您可以移至 **[語音**] > 電話號碼，在Teams系統管理中心檢視號碼和提供者。

3. **將編號指派給音訊會議橋接器。** 您可以從會議>會議橋接器> [新增] 底下的Teams系統管理中心，將編號指派給 **音訊會議網** 橋。 如需詳細資訊，請參閱[變更音訊會議橋接器上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

>[!NOTE]
>您無法將電信業者連線會議指派為橋接器的預設號碼。 一旦將電話號碼指派給音訊會議橋接器，號碼就會列在具有音訊會議授權或電信業者連線會議授權的組織使用者會議邀請中包含的 [**尋找當地號碼] 頁面** 中。
>
>若要透過電信業者路由撥出電話，請參閱本文進一步的透過 [**電信業者傳送Teams會議的撥出電話一**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)節。

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>變更使用者會議邀請中包含的預設電話號碼

 此步驟為選用。

使用者的預設電話號碼是當使用者排程會議時，其會議邀請中所包含的電話號碼。 您可以在 [使用者>管理使用者] 底下的Teams 管理員中心更新會議邀請中包含的 **電話號碼**。 若要更新使用者會議邀請中包含的電話號碼，請選取該使用者，然後選 **取 [音訊會議**] 區段中的 [**編輯**]。

套用變更之後，召集人的新會議邀請會包含新的預設電話號碼。 不過，在變更之前排定的現有會議邀請會保留原始的預設號碼。

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>透過電信業者從Microsoft Teams會議傳送撥出電話

如果您有 Microsoft 音訊會議 標準版訂閱或電信業者連線會議授權，您可以設定音訊會議服務，藉由設定音訊會議路由原則，透過電信業者傳送Teams會議的所有或一組撥出電話。

>[!NOTE]
>有了電信業者連線會議授權，撥出電話只能透過您的電信業者進行。 如果您有電信業者連線會議授權，您必須依照下述設定服務，以啟用從Teams會議到電話號碼的撥出電話。

您可以在使用者層級套用音訊會議路由原則，這表示您的電信業者只會從Teams由使用者使用相關原則召集的會議中路由撥出電話。 您也可以在全球層級套用這些原則，這表示您的電信業者會從組織中所有使用者召集的Teams會議中路由撥出來電。

使用 PowerShell 建立貴組織的新音訊會議路由原則。 若要指定運算子做為Teams會議撥出電話的主要路由，請使用指定的 PowerShell 命令，依照下列步驟進行：

1. [步驟 1：新增字串至線上 PSTN 使用原則](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [步驟 2：建立新的線上語音路由原則](#step-2-create-a-new-online-voice-route-policy)
3. [步驟 3：建立新的線上音訊會議路由原則](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [步驟 4：指派新原則給使用者](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>步驟 1：新增字串至線上 PSTN 使用原則

如需使用此 Cmdlet 的詳細資訊，請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) 。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>步驟 2：建立新的線上語音路由原則

如需使用此 Cmdlet 的 [詳細資訊，請參閱 Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) 。

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>步驟 3：建立新的線上音訊會議路由原則

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>步驟 4：指派新原則給使用者

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>若要將音訊會議路由原則設定為全域，並將它套用至貴組織中的所有使用者，您可以使用 ``-Global`` 參數而非 ``-Identity`` 參數。 例如， ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"`` .

當您建立音訊會議路由原則並將它套用至使用者時，提供參數中 ``BridgeSourcePhoneNumber`` 指定電話號碼的電信業者會將Teams撥出電話路由至 PSTN 電話號碼。 此外，參數 ``BridgeSourcePhoneNumber`` 會指定電話號碼做為撥打 PSTN 電話號碼之撥出電話的撥打線識別電話號碼。

在 RegEx 表單中 ``NumberPattern`` 指定的模式，並指定要透過您的電信業者路由的呼叫。 ``"\d+"``上述範例中的模式符合Teams會議的所有撥出電話。 您也可以將 NumberPattern 參數設為  ``"^\+1(425|206)(\d{7})$"`` ，這會將撥號與下列格式相符：+1 425 XXX XX XX 或 +1 206 XXX XX XX，或 ``"^\+1(\d{10})$"`` 是與撥號號碼相符的格式如下：+1 425 XXX XX XX。

一旦您將音訊會議路由原則指派給使用者，其會議中的所有通話都會撥打到符合其音訊會議路由原則路由電信業者所指定 RegEx 的電話號碼，包括撥打 **電話** 給我，以及透過 **[邀請某人] 或撥打電話** 會議選項撥打給我。

## <a name="manage-your-operators"></a>管理您的運算子

您可以從 [ **我的運算子]** 索引標籤檢視您的運算子、其狀態，以及對您的選擇進行下列變更：

- 依國家/地區管理電信業者服務
- 暫停運算子
- 移除運算子

>[!NOTE]
>在移除貴組織或國家/地區的電信業者之前，您必須先移除指派給使用者的所有電話號碼以及您的音訊會議橋接器，然後連絡電信業者以釋出號碼。

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>音訊會議橋接器的版本號碼

若要從Teams系統管理中心從音訊會議橋接器釋出電話號碼，請參閱在變更音訊會議 [橋接器上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)中取消指 **派會議橋接器的服務電話號碼的步驟**。

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>管理 Microsoft 音訊會議 的其他資訊

如需有關如何管理貴組織的 Microsoft 音訊會議 的其他資訊，請參閱下列文章：

- 管理貴組織的 Microsoft 音訊會議 服務設定：[在 Microsoft Teams 中管理貴組織的音訊會議設定](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- 管理貴組織中使用者的 Microsoft 音訊會議 服務設定：[在 Microsoft Teams 中管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 變更音訊會議電話號碼的自動語音應答語言：[在 Microsoft Teams 中設定音訊會議的自動語音應答語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
