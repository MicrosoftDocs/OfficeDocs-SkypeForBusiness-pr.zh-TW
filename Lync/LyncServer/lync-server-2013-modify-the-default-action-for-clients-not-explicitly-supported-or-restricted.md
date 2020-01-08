---
title: 修改未明確支援或不受限制之用戶端的預設動作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>在 Lync Server 2013 中修改未明確支援或不受限制之用戶端的預設動作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

除了指定您想要在 Lync Server 2013 環境中支援的用戶端版本之外，您也可以針對尚未定義版本原則的用戶端指定預設動作。 這可讓您限制 Lync Server 環境中使用的用戶端版本，這可以協助您控制支援多個用戶端版本所帶來的成本。

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>修改未明確支援或不受限制之用戶端的預設動作

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本**設定]。

4.  在 [**用戶端版本**設定] 頁面上，按兩下清單中的**全域**配置。

5.  在 [**編輯用戶端版本**設定] 對話方塊中，確認已選取 [**啟用版本控制**] 核取方塊，然後在 [**預設動作**] 底下，選取下列其中一項：
    
      - ****    如果用戶端版本與**用戶端版本原則**清單中的任何篩選器都不相符，允許用戶端登入。
    
      - ****    如果用戶端版本與**用戶端版本原則**清單中的任何篩選器都不相符，Block 就會防止用戶端登入。
    
      - ****    當用戶端版本與**用戶端版本原則**清單中的任何篩選器不相符，且包含可供下載較新用戶端的 url 時，使用 [以 url 封鎖] 可防止用戶端登入。
    
      - **[允許使用 URL**   ]：如果用戶端版本與**用戶端版本原則**清單中的任何篩選器不相符，則允許用戶端登入，並包含錯誤訊息，其中包含可下載較新用戶端的 URL。

6.  如果您已選取 [**封鎖] 與 [url**]，請在 [ **URL** ] 方塊中，輸入要包含在錯誤訊息中的用戶端下載 URL。

7.  按一下 [認可]****。

</div>

<div>

## <a name="to-disable-client-version-control"></a>停用用戶端版本控制

  - 若要停用版本控制，讓所有用戶端無論用戶端版本為何都要登入，請清除 [**啟用版本控制**] 核取方塊，然後按一下 [Commit] （**提交**）。

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來修改預設動作

當使用者嘗試使用未明確支援或受用戶端版本原則限制的用戶端登錄時所採取的預設動作，可以使用 Windows PowerShell 命令列介面和**CsClientVersionPolicy** Cmdlet 來管理。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>設定預設動作來封鎖存取

  - 下列命令會設定雷德蒙網站區塊的預設動作。 這會封鎖不存在用戶端版本設定規則之任何用戶端的註冊。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>設定預設動作以允許存取

  - 在這個範例中，雷德蒙網站的預設動作會設定為 [允許]。 這可讓您註冊任何不存在用戶端版本配置規則的用戶端。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

如需詳細資訊，請參閱[CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中管理裝置、電話及用戶端應用程式](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

