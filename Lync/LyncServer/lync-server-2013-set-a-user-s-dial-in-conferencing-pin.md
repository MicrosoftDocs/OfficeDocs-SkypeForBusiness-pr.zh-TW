---
title: Lync Server 2013：設定使用者的電話撥入式會議 PIN
description: Lync Server 2013：設定使用者的電話撥入式會議 PIN。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 238c2a72da81a53b409d81c1b91c885f1ddabcbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543329"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者的電話撥入式會議 PIN

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-10_

若要將電話撥入式會議加入為已驗證的使用者，使用 Active Directory 網域服務 (AD DS) 認證的 Lync Server 2013 使用者需要個人識別碼)  (PIN 碼。 如果使用者忘記電話撥入式會議 PIN，或是未使用 Lync Server 設定 PIN，您可以從 Lync Server 控制台設定使用者的 PIN 碼。 您可以自動產生 PIN 碼，也可以手動建立 PIN 碼。

<div>


> [!NOTE]  
> PIN 碼的特定特性（如其最小長度）可以設定為原則。 除了通用原則之外，您還可以為個別網站或使用者設定 PIN 原則。 如需設定 PIN 原則的詳細資訊，請參閱 <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">在 Lync Server 2013 中設定電話撥入式會議個人身分識別號碼 (PIN) 規則</A>。



</div>

<div>

## <a name="to-set-a-users-pin"></a>設定使用者的 PIN

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  使用下列其中一種方法，找到使用者：
    
      - 在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。
    
      - 如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。

5.  (選用) 指定其他搜尋條件，縮減結果：
    
    1.  按一下 **[新增篩選]**。
    
    2.  輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。
    
    3.  在 **[等於]** 下拉式清單中，按一下運算子 (例如 **[等於]** 或 **[不等於]**)。
    
    4.  視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。
        
        <div>
        

        > [!TIP]  
        > 若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。

        
        </div>
    
    5.  按一下 [尋找]****。
    
    <div>
    

    > [!NOTE]  
    > 如果 PIN 已鎖定，您必須解除鎖定 PIN，才能設定 PIN。若要解除鎖定 PIN，請依序按一下使用者、[執行]<STRONG></STRONG> 和 [解除鎖定 PIN]<STRONG></STRONG>。

    
    </div>

6.  按一下搜尋結果中的使用者，按一下 [ **動作**]，然後按一下 [ **設定 PIN**]。

7.  在 [ **設定 PIN** ] 對話方塊中，執行下列其中一項動作：
    
      - 若要允許 Lync Server 2013 產生使用者的 PIN，請選取 [ **自動產生有效的 pin** (預設) 。
    
      - 若要建立您自己的 PIN，請按一下 [ **手動輸入特定的 pin**]，然後按一下文字方塊，然後輸入符合 pin 原則設定中所指定之 pin 碼需求的 pin 碼。

8.  按一下 [確定]****。

9.  在 [ **設定 PIN**] 中，執行下列其中一項動作：
    
      - 選取 [ **顯示 pin** ] 核取方塊以查看 pin，然後複製 pin 碼，並使用組織的慣用方法將其傳送給使用者。
    
      - 按一下 [ **開啟我的電子郵件應用程式]，將新的 PIN 碼傳送給使用者** ，以便透過電子郵件傳送 pin 碼。 如果 Microsoft Office Outlook 是您的電子郵件用戶端，則 PIN 碼會自動複製到新的電子郵件中。 如果您使用不同的電子郵件用戶端，請選取 [ **顯示 pin** ] 核取方塊以查看 pin 碼，然後將其複製到您的電子郵件訊息中。

10. 按一下 **[關閉]**。

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派使用者 PIN

您也可以使用 Set-CsClientPin Cmdlet 來指派 PIN 碼號碼。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>若要自動將 PIN 碼指派給使用者

  - 下列命令會將 PIN 碼指派給使用者 Ken Myer。 因為未包含 Pin 參數，Lync Server 會自動產生並指派 PIN 碼。
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>若要將特定 PIN 碼號碼指派給使用者

  - 這個命令會使用 Pin 參數，將 PIN 碼121989指派給使用者 Ken Myer。
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

如需詳細資訊，請參閱 [unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[撥入存取號碼](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[在 Lync Server 2013 中設定電話撥入式會議個人身分識別號碼 (PIN) 規則](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

