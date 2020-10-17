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
ms.openlocfilehash: 48ee24dca1cdf083de990ef42dae4017ed927e15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524560"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中的會議遷移考慮

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-10_

本節將討論下列主題：

  - Microsoft Lync Server 2013 中的會議變更

  - 依據使用者的會議需求移轉使用者

  - 移轉現有的會議與會議內容

  - Lync Server 2010 遷移期間的使用者經驗

  - Office 通訊伺服器 2007 R2 遷移期間的使用者經驗

  - Microsoft Lync 2013 與舊版伺服器版本上的會議相容性

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Lync Server 2013 中的會議變更

**Lync Server 2013 功能。**    Lync Server 2013 提供新的會議功能，當使用者的帳戶移至 Lync Server 2013 並以 Lync 2013 用戶端登入時，這些功能就可供使用者使用。 [Lync server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)會列出新功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

**會議 URL。**    在 Lync Server 2010 中，Lync Server 2013 中的所有新排程會議都具有 URL 首碼 HTTPs://，且現有會議會隨使用者帳戶一起遷移。 不過，Lync Server 2013 不支援 Office 通訊伺服器 2007 R2 會議呼叫 (conf://URL 首碼) 或 web 會議 (meet://URL 首碼) 。 如需詳細資訊，請參閱本主題稍後的「從 Office 通訊伺服器 2007 R2 遷移會議」。

**用戶端支援。**    與 Lync Server 2010 不同的是，Lync Server 2013 不支援 Office Communicator 用戶端進行會議。 您無法使用下列用戶端加入透過 Lync 2013 之線上會議增益集排程的會議：

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

在遷移期間，Office Communicator 2007 R2 使用者應使用 Lync Web App 2013 加入 Lync Server 2013 會議，直到他們的用戶端升級為止。 請注意，Office Communicator 2007 R2 使用者可以繼續使用其現有的用戶端對 Lync Server 2013 進行顯示狀態和 IM 功能，但不支援會議功能。

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>依據使用者的會議需求移轉使用者

**頻繁會議召集人。**    請考慮在程式中及早遷移常見的會議召集人，以利用[lync server 2013 中新的會議功能](lync-server-2013-new-conferencing-features.md)所述的新 Lync server 2013 和 Lync 2013 功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

**Live Meeting 使用者。**    如果您是從 Office 通訊伺服器 2007 R2 進行遷移，且您的使用者需要使用 Live Meeting 特有的 web 會議功能（特別是對大型會議和分割的會議室的支援），您可以使用下列選項：

  - 貴公司如有提供 Live Meeting 服務，建議召集人使用這項服務。

  - 請將召集人保留在舊版的 Office 通訊伺服器上，如此一來，他們就可以繼續排程伺服器型 Live Meeting web 會議。

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>移轉現有的會議與會議內容

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>從 Lync Server 2010 遷移會議

當您將使用者從 Lync Server 2010 移至 Lync Server 2013 時，下列資訊會隨之使用者帳戶移動：

  - 使用者已排定的會議。 這包括會議目錄及會議資料。

  - 使用者的個人身分識別號碼 (PIN) 。 直到過期或使用者要求新 PIN 前，使用者目前的 PIN 都持續有效。

不過，下列使用者帳戶資訊不會移至新的伺服器：

  - 會議內容，例如 PowerPoint 簡報、白板內容和輪詢資料

若要移動會議中已共用的內容，請使用 Move-CsUser Cmdlet 的 MoveMeetingContent 參數。 如需使用此 Cmdlet 的詳細資訊，請參閱 Lync Server 2013 Cmdlet 檔中的 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 。

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>從 Office 通訊伺服器 2007 R2 遷移會議

Office 通訊伺服器 2007 R2 會議是電話會議 (conf://URL 首碼) 或網路會議 (meet://URL 首碼) 。 Lync Server 2013 不支援這些早期的 conf://和 meet://會議，也不會與使用者帳戶一起遷移。 遷移之後，您應該指示使用者更新其已排程的任何線上會議的連結。 使用者可以在安裝 Lync 2013 用戶端後，開啟已排程的會議邀請（更新會議 URL），然後將邀請重新傳送給參與者，以執行這項作業。

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Lync Server 2010 遷移期間的使用者經驗

本節提供從 Lync 2010 遷移時，使用者的會議體驗摘要。 如需 Lync Server 2013 用戶端如何共存及與舊版用戶端及伺服器版本互動的詳細資訊，請參閱 [Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>加入 lync Server 2010 與 Lync 2013 用戶端的會議

從 Lync Server 2010 遷移期間，當使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，可能會有一段共存。 這些使用者可以存取 Lync 2013 用戶端功能，但有下列例外：

  - 在 [ **參與者** 管理] 選項中，透過指向會議視窗中的 [人員] 圖示可供存取，[ **無會議 IM** ] 選項不會正常運作。

  - 圖庫 View 在影片會議中無法運作。 使用者只會看到使用中的音箱，而不是所有的揚聲器。 在 [ **選擇版面** 配置選項] 清單中，無法使用 **圖庫 View** 功能

  - 在 [影片會議] 中，預設會顯示參與者清單。

  - 以滑鼠右鍵按一下參與者清單中的使用者時，會無法使用 [影片] [影片] 和 [**固定至圖庫**]**的 [工作**表參與者管理] 選項。

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office 通訊伺服器 2007 R2 遷移期間的使用者經驗

本節提供在安裝 Lync 2013 之前和之後，從 Office 通訊伺服器 2007 R2 進行遷移時，使用者的會議體驗摘要。 如需 Lync Server 2013 用戶端如何共存及與舊版用戶端及伺服器版本互動的詳細資訊，請參閱 [Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>在遷移使用者帳戶之後，安裝 Lync 2013 之前

將使用者遷移至 Lync Server 2013 伺服器之後，但在安裝新用戶端之前，Office Communicator 2007 R2 使用者可以繼續使用其現有的2013用戶端，以進行顯示狀態和 IM 功能，但不支援會議功能。

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>在使用者帳戶遷移後，安裝 Lync 2013 之後

當已遷移的使用者安裝 Lync 2013 時，也會安裝 Lync 2013 的線上會議增益集。 此作法具有下列影響：

  - 所有在此之後排程的會議皆會使用 https:// 位址的新會議格式，而不再使用舊版的 meet:// Live Meeting 位址。

  - 在 Lync 2013 的 IT 管理部署中，管理員可以選擇卸載 Microsoft Office Outlook 的會議增益集，以用於排程 Live Meeting 伺服器和服務型會議。 不過您可能還有使用者需要排程 Live Meeting 服務會議。 此時，您可以考慮讓兩者同時並存。

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>使用舊版用戶端之同盟組織的會議

同盟組織中使用 Microsoft Office Communicator 2007 的使用者，如果召集人鎖定了該會議，則無法在組織中加入 Lync Server 2013 會議。 您必須在 Lync Server 2013 中重排這些會議，以便在同盟參與者使用新的 HTTPs://會議 URL 加入會議時，他們可以使用 Lync Web App。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

