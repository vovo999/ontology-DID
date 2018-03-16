[中文版](./README_cn.md)


<h1 align="center">ONT ID 身份标识协议及信任框架 </h1>
<h4 align="center">版本 V0.6.0 </h4>

## 概述

ONT ID是一个去中心化的身份标识协议，支持各类实体包括人、组织机构、物品及内容的分布式和多样化的确权、识别、认证等协同服务。ONT ID为每个主体建立基于密码学的数字身份，使得数据授权、确权自主化，使身份和数据真正变为用户可以掌控的资产。ONT ID具有去中心化、自主管理、隐私保护、安全易用等特点。

基于ONT ID的和完整的分布式身份协同框架通过可验证声明协议建立去中心化的信任模型和分布式信任传递体系，同时引入C-L签名算法、西格玛协议等密码学技术来实现可验证声明的隐私保护。同时本体还将基于ONT ID纳入各种认证服务机构，建立对主体身份的多源认证，实现完整身份画像。

* **中心化的信任模型**
此模型下，由一个或一群特定的实体作为信任锚，实体间的信任关系基于信任锚建立。信任锚指定其所信任的实体，被指定的实体又可指定其信任的其他实体。如此，以一个信任锚为源头，构建起一个信任传递的关系树。树上的每个节点有一条通向信任锚的路径，即为其信任链。任何承认该信任锚的实体在与树中的节点交互时，通过验证其信任链即可判断其是否可信。
目前最成熟、应用最广的PKI体系[7]就是一种中心化的信任模型。用户首先向作为信任锚的认证中心申请一个数字证书。认证中心对申请者审查通过后，将其身份信息和公钥写入数字证书，并附加认证中心的数字签名。通过认证中心签发的数字证书即认证了用户的身份和公钥的绑定关系，任何人都可以使用认证中心的公钥来验证该证书的真伪，进而使用证书中的公钥验证用户的签名，确认其身份。同时拥有数字证书的用户还可以申请作为下级认证者对其它用户颁发数字证书，其颁发的数字证书的效力最终由认证中心保证。在PKI模型中，任何参与方都必须无条件的信任认证中心，信任关系通过实体间的数字签名从认证中心逐层传递下去。
中心化的信任模型有很多优点，其严谨的信任传递方式、清晰明确的信任与非信任边界在很多场景下都是很好的特性，解决了现实中的很多问题。然而中心化的信任模式也存在一定的缺陷，除了需要无条件信任锚，对其诚实性及安全性由较高的要求以外，对于现实世界的复杂信任关系，这种依赖于中心节点的模式会严重限制应用的灵活性。

* **去中心化的信任模型** 
除了依赖特定的中心实体构建信任关系以外，实体之间还能够自发、对等地产生信任关系。信任的传递由实体间的相互认证实现。一个实体被数量越多的实体认证，其可信度就越高；被可信度越高的实体认证的实体，亦将获得更高的可信度。
去中心化的信任模型是一种模糊的信任模型，并没有统一、清新的信任边界，在不同的场景下可以根据不同的信任评估方法评估实体的信任度。正是由于这种高度的灵活性，在现实生活中具有广泛的用途。

## 协议介绍

### **身份标识协议**

实体是指现实世界中的个人、组织（组织机构、企事业单位等）、物品（手机、汽车、IOT设备等）、内容（文章、版权等），而身份是指实体在网络上的对应标识。本体网络使用本体身份标识（ONT ID）来标识和管理实体在链上的数字身份。在本体区块链上，一个实体可以对应到多个身份标识，且多个身份标识之间没有任何关联。

[>> 了解更多](http://git.ont.network/??)

### **可验证申明协议**

可验证申明是指，一个实体对另一个实体（包括自己）的某些属性作出的描述性声明，并附加自己的数字签名，用以证明这些属性的真实性，可被其他实体验证。可验证申明协议详细描述了声明的签发、存储、验证等流程及规范。

[>> 了解更多](http://git.ont.network/??)

## 参与者说明

* **用户** ONT ID的最终使用者。 
* **验证服务提供商** 验证服务Verification Provider是指在本体生态上提供认证服务的合作方，其可能是政府机关、大学、银行、第三方认证服务机构（比如CA机构）、生物识别科技公司等等，这些企业为本体ONT ID的持有者（Owner）提供多维度的认证，并第一时间通过Ontology BlockChain来记录认证行为和认证结果HASH，从而为用户认证需求方/场景方提供了标准化、可信的认证方式。
* **DApp开发者** 基于ONT ID协议和接口为用户和场景方提供各种应用开发。


## 开始使用

ONT ID不仅仅是一个协议，整个体系已经被完整地通过智能合约实现在本体区块链上，您只需要操作我们的各种SDK或者RPC接口，即可使用ONT ID。

在使用平台之前，我们需要您首先明确您地角色，根据角色来去了解

### DApp开发者
如果您是DApp开发者，我们建议您从[>>开发指南](./docs/en/get_started.md)开始了解ONT ID及信任框架吧，当然您也可以直接开始使用以下这些接口。

* [>> JAVA SDK](ont-sdk-java.md) 

* [>> TS SDK](ont-sdk-ts.md)  

### 验证服务提供商
如果您是验证服务提供商，请进入[>> 验证服务商接入标准](./docs/en/verification_provider_specification.md)了解详细情况。




