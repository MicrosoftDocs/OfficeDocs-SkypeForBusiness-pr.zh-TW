---
title: Lync Server 2013：查看會議配置設定
description: Lync Server 2013：查看會議配置設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190b9d331a8cd0a08e17c482dbc3b0bc27590003
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576399"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看會議配置設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在 [Lync Server 2013 控制台] 中，您可以使用會議設定設定來控制如何在部署中實施會議。 這包括下列會議設定：

  - 當您部署 Lync Server 2013 時，預設會建立全域設定。

  - 選用的網站層級和使用者層級設定，可讓您建立及用來指定如何為特定網站或使用者實施會議。

<div>

## <a name="to-view-meeting-configuration-settings"></a>若要查看會議配置設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **會議** ]，然後按一下 [ **會議**設定]。

4.  在 [ **會議** 設定] 頁面上，按一下您要查看的會議設定。

5.  在 [ **編輯檔案篩選**] 中，選取 [ **顯示詳細資料]。** 核取方塊。
    
    **編輯會議設定- \<policy\> **開啟顯示選取原則的設定。 如需設定設定的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改會議配置設定的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看會議設定資訊

您可以使用 Windows PowerShell 和 Get-CsMeetingConfiguration Cmdlet 來查看會議設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-meeting-configuration-information"></a>若要查看會議設定資訊

  - 若要查看所有會議設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsMeetingConfiguration
    
    如此將傳回類似如下的資訊：
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

如需詳細資訊，請參閱 [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

