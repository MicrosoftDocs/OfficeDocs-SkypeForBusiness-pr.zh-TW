---
title: Lync Server 2013：設定語音信箱重新路由設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f327bfc533b28313e4728b13c7a69d6c16bc034
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定語音信箱重新路由設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

Survivable 分支裝置和 Survivable 分支伺服器可在 WAN 中斷期間為分支使用者提供語音信箱留存能力，如果已在中央網站安裝 Exchange 整合通訊 (UM) ，且已部署 Exchange UM 郵件自動語音應答 (AA) 。 建議您的 Exchange 系統管理員應將 AA 設定成僅接受訊息，而停用其他一般功能 (例如轉接給使用者或轉接給操作員)。 或者，您也可以使用一般 AA 或自訂 AA 來路由電話。

如需詳細資訊，請參閱規劃檔中的「準備語音信箱留存功能」一節中的[Lync Server 2013 分支網站恢復需求](lync-server-2013-branch-site-resiliency-requirements.md)。

<div>

## <a name="to-configure-voice-mail-survivability"></a>若要設定語音信箱存續能力

1.  請您的 Exchange 管理員設定 AA 只接受 Exchange 命令介面中 (的郵件： **Set-UMAutoAttendant \< AA name \> -CallSomeoneEnabled $false**。 指定要允許留言的參數 (*SendVoiceMsgEnabled*) 預設為 true。

2.  在 Lync Server 管理命令介面中，使用**New-CSVoiceMailReroutingConfiguration** Cmdlet，將 AA 電話號碼設定為 Survivable Branch 裝置或 Survivable branch Server 上之語音信箱重新路由設定中的 Exchange UM 自動語音應答電話號碼。
    
    <div>
    

    > [!NOTE]  
    > 如果您之後需要修改語音信箱重新路由設定，請使用 <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> Cmdlet 來執行。 如需 <STRONG>New-</STRONG> 和 <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> 的詳細資訊，請參閱命令介面的說明主題。

    
    </div>

3.  將對應至分支使用者之 Exchange UM 撥號對應表的 Exchange UM 訂戶存取號碼，設定為 Survivable Branch 裝置或 Survivable Branch Server 上之語音信箱重新路由設定中的 Exchange UM 訂戶存取號碼。
    
    <div>
    

    > [!NOTE]  
    > 設定 Exchange UM 使用者的撥號對應表，讓所有需要存取 WAN 中斷期間之 Get Voice Mail 功能的分支使用者都有關聯的撥號對應表。

    
    </div>

Survivable 分支裝置或 Survivable Branch 伺服器的**下一個步驟**：在[Lync Server 2013 中的 Survivable Branch 裝置或伺服器上，家用使用者](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

