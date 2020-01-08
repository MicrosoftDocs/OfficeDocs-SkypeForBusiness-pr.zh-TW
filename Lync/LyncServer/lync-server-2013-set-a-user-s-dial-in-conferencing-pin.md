---
title: Lync Server 2013：設定使用者的電話撥入式會議 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258c6e5da1dc5b78d53bbc3779d50890935d7b58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者的電話撥入式會議 PIN

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-10_

若要將電話撥入式會議加入為經過驗證的使用者，擁有 Active Directory 網域服務（AD DS）認證的 Lync Server 2013 使用者需要個人識別碼（PIN）。 如果使用者忘記電話撥入式會議 PIN，或尚未使用 Lync Server 設定 PIN，您可以從 Lync Server [控制台] 設定使用者的 PIN。 您可以自動產生 PIN 或手動建立。

<div>


> [!NOTE]  
> PIN 的特定特性（例如其最小長度）可以設定為原則。 除了全域原則之外，您還可以為個別的網站或使用者設定 PIN 原則。 如需有關設定 PIN 原則的詳細資訊，請參閱<A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">在 Lync Server 2013 中設定電話撥入式會議個人識別碼（PIN）規則</A>。



</div>

<div>

## <a name="to-set-a-users-pin"></a>若要設定使用者的 PIN

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  使用下列其中一種方法來尋找使用者：
    
      - 在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。
    
      - 如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。

5.  可選指定額外的搜尋準則以縮小結果範圍：
    
    1.  按一下 [**新增篩選**]。
    
    2.  輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。
    
    3.  在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。
    
    4.  根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。
        
        <div>
        

        > [!TIP]  
        > 若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。

        
        </div>
    
    5.  按一下 [**尋找**]。
    
    <div>
    

    > [!NOTE]  
    > 如果 PIN 已鎖定，您必須先解除鎖定 PIN，才能進行設定。 若要解除鎖定 PIN，請按一下使用者，按一下 [<STRONG>動作</STRONG>]，然後按一下 [<STRONG>解除鎖定 pin</STRONG>]。

    
    </div>

6.  在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**設定 PIN**]。

7.  在 [**設定 PIN** ] 對話方塊中，執行下列其中一項操作：
    
      - 若要允許 Lync Server 2013 產生使用者的 PIN，請選取 [**自動產生有效的 pin** （預設值）]。
    
      - 若要建立您自己的 PIN，請按一下 [**手動輸入特定 PIN**]，按一下文字方塊，然後輸入符合 pin 原則設定中所指定 pin 需求的 pin。

8.  按一下 [確定]****。

9.  在 [**設定 PIN**] 中，執行下列其中一項操作：
    
      - 選取 [**顯示 pin** ] 核取方塊以查看 pin，然後複製 pin，並使用貴組織的慣用方法將它與使用者進行通訊。
    
      - 按一下 [**開啟我的電子郵件應用程式]，將新的 PIN 傳送給使用者**，即可透過電子郵件傳送 pin。 如果 Microsoft Office Outlook 是您的電子郵件用戶端，則 PIN 會自動複製到新的電子郵件訊息中。 如果您使用不同的電子郵件用戶端，請選取 [**顯示 pin** ] 核取方塊以查看 pin，然後將它複製到您的電子郵件訊息中。

10. 按一下 [**關閉**]。

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派使用者 PIN

您也可以使用 CsClientPin Cmdlet 來指派 PIN 碼。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>自動將 PIN 號碼指派給使用者

  - 下列命令會將 PIN 碼指派給使用者 Ken Myer。 因為未包含 Pin 參數，所以 Lync Server 會自動產生並指派 PIN 碼。
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>將特定的 PIN 碼指派給使用者

  - 這個命令會使用釘選參數，將 PIN 碼121989指派給使用者 Ken Myer。
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

如需詳細資訊，請參閱[CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[撥入存取號碼](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))  


[在 Lync Server 2013 中設定電話撥入式會議個人身分識別號碼（PIN）規則](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

