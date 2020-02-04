---
title: Lync Server 2013：註冊智慧卡驗證的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中註冊智慧卡驗證的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

有兩種方法可以為使用者註冊智慧卡驗證。 更簡單的方法是讓使用者使用 web 註冊直接註冊智慧卡驗證，而更複雜的方法則涉及使用註冊代理程式。 本主題主要針對智慧卡憑證的自行註冊。

如需以註冊代理代表使用者註冊的詳細資訊，請參閱代表其他使用者註冊憑證[http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)。

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>註冊使用者的智慧卡驗證

1.  使用啟用 Lync 的使用者認證登入 Windows 8 工作站。

2.  啟動 Internet Explorer。

3.  流覽至 [**憑證授權單位 Web 註冊**] 頁面（ https://MyCA.contoso.com/certsrv)例如
    
    <div>
    

    > [!NOTE]  
    > 如果您使用的是 Internet Explorer 10，您可能需要以相容模式查看此網站。

    
    </div>

4.  在 [**歡迎**] 頁面上，選取 [**要求憑證**]。

5.  接著，選取 [**高級要求**]。

6.  選取 [**建立並提交此 CA 的要求**]。

7.  選取 [**憑證範本**] 區段底下的 [**智慧卡使用者**]，並以下列值完成高級憑證要求：
    
      - [**主要選項**] 請確認他追蹤下列設定：
        
          - 選取 [**建立新金鑰集**] 選項按鈕
        
          - 針對**CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]
        
          - 如需**金鑰用法**，請選取 [ **Exchange** ] （這是唯一可用的選項）。
        
          - 針對**金鑰大小**，請輸入**2048**
        
          - 確認已選取 [**自動金鑰容器名稱**]
        
          - 不要選取其他方塊。
    
      - 在 [**其他選項**] 底下，確認下列值：
        
          - 針對**要求格式**，請選取 [ **CMC**]。
        
          - 針對**雜湊演算法**選取 [ **sha1**]。
        
          - 針對**易記名稱**，請輸入**Smardcard 憑證**。

8.  如果您使用的是物理智慧卡讀取器，請將智慧卡插入裝置中。

9.  按一下 [**提交**] 以提交證書申請。

10. 出現提示時，請輸入用來建立虛擬智慧卡的 PIN。
    
    <div>
    

    > [!NOTE]  
    > 預設的虛擬智慧卡 PIN 值是 "12345678"。

    
    </div>

11. 在頒發憑證之後，按一下 [**安裝此憑證**] 以完成註冊程式。
    
    <div>
    

    > [!NOTE]  
    > 如果您的憑證要求失敗，並出現「此網頁瀏覽器不支援產生憑證要求」錯誤，有三種可能的方法可以解決此問題： 
    > <OL>
    > <LI>
    > <P>在 Internet Explorer 中啟用 [相容性] 視圖</P>
    > <LI>
    > <P>在 Internet Explorer 中啟用 [開啟 Intranet 設定] 選項</P>
    > <LI>
    > <P>在 Internet Explorer [選項] 功能表中，選取 [安全性] 索引標籤底下的 [重設所有區域為預設層級] 設定</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

