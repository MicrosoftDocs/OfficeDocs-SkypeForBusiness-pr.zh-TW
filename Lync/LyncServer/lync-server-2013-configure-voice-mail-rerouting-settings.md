---
title: Lync Server 2013：設定語音信箱重新路由設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定語音信箱重新路由設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

如果您已在中央網站安裝 Exchange 整合通訊（UM），且已部署 Exchange UM 訊息自動語音應答（AA），Survivable 分支裝置和 Survivable 分支伺服器可以在 WAN 停機期間提供語音信箱給分支使用者。 我們建議您的 Exchange 管理員將 AA 設定為僅接受訊息，這會停用其他一般功能，例如轉接給使用者或傳送到操作員。 或者，您可以使用一般的 AA 或自訂的 AA 來傳送通話。

如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 分支網站復原需求](lync-server-2013-branch-site-resiliency-requirements.md)中的 [準備語音信箱留存] 區段。

<div>

## <a name="to-configure-voice-mail-survivability"></a>設定語音信箱的留存能力

1.  要求 Exchange 管理員將 AA 設定為僅接受訊息（在 Exchange Shell 中使用下列 Cmdlet： **UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**。 指定允許離開郵件（*SendVoiceMsgEnabled*）的參數預設為 true。

2.  在 Lync Server 管理命令介面中，使用**新的 CSVoiceMailReroutingConfiguration** Cmdlet，將 AA 電話號碼設定為 Survivable 分支裝置或 Survivable 分支伺服器上的語音信箱重新路由設定中的 Exchange UM 自動語音應答電話號碼。
    
    <div>
    

    > [!NOTE]  
    > 如果您稍後需要修改語音信箱重新路由設定，請使用<STRONG>CsVoiceMailReRoutingConfiguration</STRONG> Cmdlet 來執行此動作。 如需有關 CSVoiceMailReroutingConfiguration 的詳細資訊，請參閱 Shell 說明主題中的 [<STRONG>新增</STRONG>] 與 [<STRONG>設定</STRONG>]。

    
    </div>

3.  將與分支使用者 Exchange UM 撥號方案對應的 Exchange UM 使用者存取號碼設定為 Exchange UM 使用者存取號碼（在 Survivable 分支裝置或 Survivable 分支伺服器上的語音信箱重新路由設定中）。
    
    <div>
    

    > [!NOTE]  
    > 設定 Exchange UM 使用者的撥號計畫，以便在 WAN 停機期間需要存取 [取得語音信箱] 功能的所有分支使用者都有一個相關聯的撥號方案。

    
    </div>

Survivable 分支裝置或 Survivable 分支伺服器的**下一個步驟**：在[Lync Server 2013 的 Survivable 分支裝置或伺服器上的家用使用者](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

