:orphan:

####################
Account Link Schemas
####################

.. note:: The `catbuffer schemas <https://github.com/nemtech/catbuffer>`_ repository defines how each transaction type should be serialized. In combination with the `catbuffer-generators <https://github.com/nemtech/catbuffer-generators>`_ project, developers can generate builder classes for a given set of programming languages. 

****************
Account Key Link
****************

.. _account-key-link-transaction:

AccountKeyLinkTransaction
=========================

Announce an AccountKeyLinkTransaction to delegate the account importance score to a proxy account.
Required for all accounts willing to activate delegated harvesting.

**Version**: 0x01

**EntityType**: 0x414C

**Inlines**:

* :ref:`Transaction <transaction>` or :ref:`EmbeddedTransaction <embedded-transaction>`

.. csv-table::
    :header: "Property", "Type", "Description"
    :delim: ;

    linkedPublicKey; :schema:`Key <types.cats>`; Linked public key.
    linkAction; :ref:`LinkAction <link-action>`; Account link action.

.. _link-action:

LinkAction
==========

Enumeration: uint8

.. csv-table::
    :header: "Id", "Description"
    :delim: ;

    0x00; Unlink account.
    0x01; Link account.

*************
Node Key Link
*************

.. _node-key-link-transaction:

NodeKeyLinkTransaction
======================

Announce a NodeKeyLinkTransaction to link a public key to an account.
TLS uses the linked public key to create sessions.
Required for node operators.

**Version**: 0x01

**EntityType**: 0x424C

**Inlines**:

* :ref:`Transaction <transaction>` or :ref:`EmbeddedTransaction <embedded-transaction>`

.. csv-table::
    :header: "Property", "Type", "Description"
    :delim: ;

    linkedPublicKey; :schema:`Key <types.cats>`; Linked public key.
    linkAction; :ref:`LinkAction <link-action>`; Account link action.