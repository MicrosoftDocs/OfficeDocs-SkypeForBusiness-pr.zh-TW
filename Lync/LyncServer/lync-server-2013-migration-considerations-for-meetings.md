---
title: Lync Server 2013：會議的遷移考慮
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中的會議遷移考慮

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-10_

本節將討論下列主題：

  - 在 Microsoft Lync Server 2013 中對會議所做的變更

  - 根據其會議需求來遷移使用者

  - 遷移現有的會議與會議內容

  - 在 Lync Server 2010 遷移期間的使用者體驗

  - Office 通訊伺服器 2007 R2 遷移期間的使用者體驗

  - Microsoft Lync 2013 與舊版伺服器版本的會議相容性

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Lync Server 2013 中的會議變更

**Lync Server 2013 功能。**   Lync server 2013 提供新的會議功能，在使用者的帳戶移至 lync Server 2013 並以 lync 2013 用戶端登入之後，使用者就能使用。 新功能在[Lync server 2013 的新會議功能](lync-server-2013-new-conferencing-features.md)中有說明，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

**會議 URL。**   就像在 lync server 2010 中，lync server 2013 中所有新近排程的會議都有 HTTPS://的 URL 首碼，而現有的會議則與使用者帳戶一起遷移。 不過，Lync Server 2013 不支援 Office 通訊伺服器 2007 R2 會議呼叫（conf://URL 首碼）或 web 會議（meet://URL 首碼）。 如需詳細資訊，請參閱本主題稍後的「從 Office 通訊伺服器 2007 R2 遷移會議」。

**用戶端支援。**   與 lync server 2010 不同，lync server 2013 不支援 Office Communicator 用戶端進行會議。 您無法使用下列用戶端來加入透過 Lync 2013 的線上會議增益集排程的會議：

  - Office Communicator 2007 R2

  - Microsoft Office 通訊伺服器 2007 R2 助理

  - Office Communicator 2007

  - Office Live Meeting 2007

在遷移期間，Office Communicator 2007 R2 使用者應該使用 Lync Web App 2013 加入 Lync Server 2013 會議，直到他們的用戶端升級為止。 請注意，Office Communicator 2007 R2 使用者可以繼續針對 Lync Server 2013 使用現有的用戶端，以取得目前狀態與 IM 功能，但不支援會議功能。

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>根據其會議需求來遷移使用者

**經常會議召集人。**   考慮在程式的早期階段遷移會議召集人，讓他們可以利用[lync Server 2013 中新](lync-server-2013-new-conferencing-features.md)的 [會議] 功能所述的新 Lync server 2013 和 Lync 2013 功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

**Live Meeting 使用者。**   如果您是從 Office 通訊伺服器 2007 R2 進行遷移，且您的使用者需要使用 Live Meeting 所特有的 web 會議功能，就是您可以使用下列選項：

  - 建議召集人使用 Live Meeting 服務（如果您的組織中有提供）。

  - 將召集人留在舊版 Office 通訊伺服器上，讓他們可以繼續排程以伺服器為基礎的 Live Meeting web 會議。

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>遷移現有的會議與會議內容

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>從 Lync Server 2010 遷移會議

當您將使用者從 Lync Server 2010 移至 Lync Server 2013 時，下列資訊會與使用者帳戶一起移動：

  - 已由使用者排程的會議。 這包含會議目錄和會議資料。

  - 使用者的個人身分識別號碼（PIN）。 使用者目前的 PIN 會持續起作用，直到過期為止，或使用者要求新的 PIN。

不過，下列使用者帳戶資訊不會移到新伺服器：

  - 會議內容，例如 PowerPoint 簡報、白板內容，以及投票資料

若要移動已在會議中共用的內容，請使用 Move-csuser Cmdlet 的 MoveMeetingContent 參數。 如需有關使用此 Cmdlet 的詳細資訊，請參閱 Lync Server 2013 Cmdlet 檔中的[移動流覽 move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 。

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>從 Office 通訊伺服器 2007 R2 遷移會議

Office 通訊伺服器 2007 R2 會議可以是電話會議（conf://URL 首碼）或網路會議（meet://URL 首碼）。 Lync Server 2013 不支援這些較舊的 conf://和 meet://會議，且不會與使用者帳戶一起遷移。 遷移之後，您應該指示使用者更新已排程之任何線上會議的連結。 他們可以在安裝 Lync 2013 用戶端後執行此動作，方法是開啟已排程的會議邀請，這會更新會議 URL，並重新傳送邀請給參與者。

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>在 Lync Server 2010 遷移期間的使用者體驗

本節提供從 Lync 2010 遷移時使用者的會議體驗摘要。 如需有關 Lync Server 2013 用戶端如何共存以及與舊版用戶端和伺服器版本互動的詳細資訊，請參閱[Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>使用 Lync 2013 用戶端加入 Lync Server 2010 會議

從 Lync Server 2010 遷移期間，您可能會在使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，共存一段時間。 這些使用者可以存取 Lync 2013 用戶端的功能，但有下列例外狀況：

  - 在**參與者**管理選項（可透過指向會議視窗中的 [人員] 圖示來存取），[**無會議 IM** ] 選項不起作用。

  - [圖庫] 視圖在視訊會議中不起作用。 使用者只會看到現用喇叭，而不是所有喇叭。 在 [**挑選版面**配置選項] 清單中，[**庫視圖**] 無法使用

  - 「參與者清單」預設會顯示在 [視訊會議] 中。

  - 在參與者清單中以滑鼠右鍵按一下使用者時，無法使用 [**鎖定影片焦點**] 和 [**釘選到圖庫**] 參與者管理選項。

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office 通訊伺服器 2007 R2 遷移期間的使用者體驗

本節提供在安裝 Lync 2013 之前和之後從 Office 通訊伺服器 2007 R2 進行遷移時的使用者會議體驗摘要。 如需有關 Lync Server 2013 用戶端如何共存以及與舊版用戶端和伺服器版本互動的詳細資訊，請參閱[Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>在已遷移使用者帳戶之後，安裝 Lync 2013 之前

在使用者遷移至 Lync Server 2013 伺服器之後，但在安裝新的用戶端之前，Office Communicator 2007 R2 使用者可以繼續針對 Lync Server 2013 使用現有的用戶端，以瞭解目前狀態與 IM 功能，但是會議功能不會受.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>在已安裝 Lync 2013 之後，進行使用者帳戶遷移之後

當已遷移的使用者安裝 Lync 2013 時，也會安裝 Lync 2013 的線上會議增益集。 這會產生下列效果：

  - 所有後續排程的會議都會使用新的會議格式，這會使用 HTTPs://位址，而不是舊版 meet://Live 會議位址。

  - 在 Lync 2013 的 IT 管理部署中，系統管理員可以選擇卸載 Microsoft Office Outlook 的會議增益集，這是用來排程 Live Meeting 伺服器與服務的會議。 不過，您可能需要繼續排程 Live Meeting 服務會議的使用者。 在這種情況下，您可以允許兩個增益集共存。

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>與使用舊版客戶的同盟組織進行會議

使用 Microsoft Office Communicator 2007 的同盟組織中的使用者，如果召集人已鎖定這些會議，則無法加入貴組織中的 Lync Server 2013 會議。 您必須在 Lync Server 2013 中重新安排這些會議，以便在聯盟參與者使用新的 HTTPs://會議 URL 加入會議時，他們可以使用 Lync Web App。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

