---
title: Lync Server 2013：查看使用者 PIN 資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1e6f8e12e7b6d2dde684a4cf558eec0ece216a9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看使用者 PIN 資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

若要將電話撥入式會議加入為經過驗證的使用者，擁有 Active Directory 網域服務（AD DS）認證的 Lync Server 2013 使用者需要個人識別碼（PIN）。 您可以從 Lync Server 2013 的 [控制台] 中查看使用者的 PIN 資訊。

<div>


> [!NOTE]  
> 您可以查看 PIN 狀態資訊，例如，PIN 是否已設定，或是 PIN 上次變更的時間，但是您看不到目前的 PIN，只需要查看 PIN 狀態即可。 如果使用者遺失其 PIN，您可以按照在<A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013 中設定使用者的電話撥入式會議 PIN</A>中的程式來重設它。



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>在 Lync Server [控制台] 中查看使用者的 PIN

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

6.  在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**查看 PIN 狀態**]。

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看使用者 PIN 資訊

您可以使用 CsClientPinInfo Cmdlet 來查看使用者 PIN 資訊。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-user-pin-information"></a>若要查看使用者 PIN 資訊

  - 若要查看使用者的 PIN 資訊，請在 Lync Server 管理命令介面中輸入類似以下的命令，然後按 ENTER：
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    這會傳回如下所示的資訊：
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

如需詳細資訊，請參閱[CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定使用者的電話撥入式會議 PIN](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[鎖定或解除鎖定 Lync Server 2013 中的使用者 PIN](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

