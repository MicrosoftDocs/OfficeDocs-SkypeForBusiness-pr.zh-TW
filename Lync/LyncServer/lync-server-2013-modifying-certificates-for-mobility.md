---
title: Lync Server 2013：修改行動的憑證
description: Lync Server 2013：修改行動的憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555849"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>在 Lync Server 2013 中修改行動憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-20_

為了支援 Lync 環境與行動用戶端之間的安全連線，您的 Director 集區、前端集區和反向 proxy 的安全通訊端層 (SSL) 憑證必須使用其他的主體替代名稱來更新， (SAN) 專案。 如果您需要深入瞭解行動之憑證需求的詳細資訊，請參閱在 [Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)中的憑證需求一節，但基本上您必須使用包含的其他 SAN 專案從憑證授權單位單位取得新憑證，然後再使用本文的步驟來新增這些憑證。

當然，您開始之前，最好知道您的憑證已有哪些主體替代名稱。 如果您不確定已設定的內容，有許多方法可供您尋找。[！附注] 當您執行 **Get-CsCertificate** 及其他 PowerShell 命令以查看此資訊時， (在預設會) 透過此逐步進行的資料將會被截斷，所以您可能不會看到所有需要的屬性。 為了取得良好的憑證及其所有內容，您可以移至 Microsoft Management Console (MMC) 並載入 [憑證] 嵌入式管理單元， (我們也會逐步進行) ，您也可以只存回 Lync Server 部署嚮導。

如以上所述，下列步驟會逐步引導您使用 Lync Server 管理命令介面和 MMC 更新憑證。 如果您想要改為在 Lync Server 部署嚮導中使用憑證嚮導，請參閱設定 director 或 Director 集區的 [Lync server 2013 中的 director 憑證](lync-server-2013-configure-certificates-for-the-director.md) （如果您設定了一個 (您可能沒有) ）。 若為前端伺服器或前端集區，您會想要 [在 Lync server 2013 中查看 [設定伺服器的憑證](lync-server-2013-configure-certificates-for-servers.md)]。

您需要記住的最後一件事是，您的 Lync Server 2013 環境中可能有單一預設憑證，也可能會有預設 (的個別憑證，也就是 web 服務) 、WebServicesExternal 及 WebServicesInternal 的所有內容。 不管您的設定為何，這些步驟都應協助您執行。

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>使用 Lync Server 管理命令介面來更新具有新主體替代名稱的憑證

1.  您必須使用具有本機系統管理員許可權的帳戶登入 Lync Server 2013 伺服器。 此外，如果您正在執行步驟12和之後的 PowerShell **Request-CsCertificate** ，該帳戶必須具有指定的憑證授權單位 (CA) 的許可權。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在您可以指派更新的憑證之前，您需要瞭解已指派給伺服器的憑證和使用類型。 在命令列中輸入：
    
        Get-CsCertificate

4.  請複查上一個步驟的輸出，以查看是否已指派單一憑證進行多種使用，或是否指派不同的憑證供每次使用。 請查看使用參數，以找出使用憑證的方式。 針對所顯示的憑證比較 Thumbprint 參數，看看相同的憑證是否有多個用途。 請留意指紋參數。

5.  更新憑證。 在命令列中輸入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如，如果 **Get-CsCertificate** Cmdlet 顯示使用 Default 的憑證，另一個使用 WebServicesInternal 的憑證，另一個使用 WebServicesExternal 的指紋值，在命令列中，您應該輸入：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要事項：**
    
    如果為每次使用指派個別的憑證 (因此，您上述檢查的指紋值因每個憑證) 而不同，因此您 **不** 需要以多種類型執行 **Set-CsCertificate** Cmdlet，如上述範例所示。 在此情況下，要為每個用途個別執行 **Set-CsCertificate** Cmdlet。 例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  若要查看憑證 (或憑證) ，請按一下 [ **開始**]，然後按一下 [ **執行 ...**]。 鍵入 MMC 以開啟 Microsoft Management Console。

7.  從 MMC 功能表中，依序選取 **[檔案]**、**[新增/移除嵌入式管理單元…]** 和 [憑證]。 按一下 **[新增]**。 出現提示時，選取 **[電腦帳戶]**，然後按 **[下一步]**。

8.  如果這是憑證所在的伺服器，請選取 [ **本機電腦**]。 如果憑證位於另一部電腦上，則應該選取**另一**部電腦，然後您可以輸入電腦的完整功能變數名稱，或按一下 [在**輸入要選取的物件名稱**] 中的 **[流覽]** ，然後輸入電腦的名稱。 按一下 **[檢查名稱]**。 當電腦的名稱解析時，它會加上底線。 依序按一下 **[確定]** 和 **[完成]**。 按一下 **[確定]** 以認可選取項目，然後關閉 **[新增/移除嵌入式管理單元]** 對話方塊。

9.  如果要檢視憑證的屬性，依序展開 **[憑證]** 和 **[個人]**，然後選取 **[憑證]**。選取要檢視的憑證，用滑鼠右鍵按一下憑證，然後選取 **[開啟]**。

10. 在 **[憑證]** 檢視中，選取 **[詳細資料]**。您可以在此處選取 **[主體]** 來選取憑證主體名稱，隨即顯示指派的主體名稱和相關屬性。

11. 若要查看指派的主體替代名稱，請選取 [ **主體替代名稱**]。 所有指派的主體替代名稱會顯示在這裡。 此處找到的主體替代名稱預設為「 **DNS 名稱** 」類型。 若 IPv6 AAAA) 記錄，您應該會看到下列成員 (所有應該是的功能變數名稱（如 DNS 主機中所述） (A 或（如果有的話）：
    
      - 此集區的集區名稱，如果這不是集區，則為單一伺服器名稱
    
      - 被指派憑證的伺服器名稱
    
      - 簡單 URL 記錄，通常為 meet 和 dialin
    
      - Web 服務的內部及 Web 服務外部名稱 (例如，webpool01.contoso.net、webpool01.contoso.com) ，其依據拓撲產生器和透過 ridden Web 服務選取範圍內的選擇。
    
      - 如果已指派，則 lyncdiscover。\<sipdomain\> 和 lyncdiscoverinternal。\<sipdomain\> 記錄。
    
    最後一個專案是您最感興趣的專案–如果有 lyncdiscover 和 lyncdiscoverinternal SAN 專案。
    
    如果您有多個要檢查的憑證，請重複這些步驟。 取得此資訊之後，即可關閉憑證檢視和 MMC。

12. 如果自動探索服務主體替代名稱遺漏，而您對 Default、WebServicesInternal 和 WebServiceExternal 類型使用單一 Default 憑證，請執行下列動作：
    
      - 在 Lync Server 管理命令介面命令列提示字元處，輸入：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有許多 SIP 網域，您就無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，您必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。 例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 如果要指派憑證，請鍵入：
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 “Thumbprint” 代表對新發行的憑證顯示的指紋。

13. 若為 Default、WebServicesInternal 和 WebServicesExternal 使用個別憑證時遺失內部自動探索 SAN，請執行下列作業：
    
      - 在 Lync Server 管理命令介面命令列提示字元處，輸入：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有許多 SIP 網域，您就無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。 例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 針對遺漏的外部自動探索主體替代名稱，在命令列中輸入：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有許多 SIP 網域，您就無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。 例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 如果要指派個別憑證類型，請鍵入：
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 “Thumbprint” 代表對新發行的個別憑證顯示的指紋。
    
    <div>
    

    > [!NOTE]  
    > 請注意，只有在執行步驟12和13的帳戶有權存取具有適當許可權的憑證授權單位單位時，才應執行步驟12和13。 如果您無法使用具有這些許可權的帳戶登入，或是您為憑證使用 public 或 remote 憑證授權，則您必須透過 Lync Server 部署嚮導要求他們，在本文頂端已深入瞭解。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

