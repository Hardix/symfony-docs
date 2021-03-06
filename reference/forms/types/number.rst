.. index::
   single: Forms; Fields; number

number Field Type
=================

Renders an input text field and specializes in handling number input. This
type offers different options for the precision, rounding, and grouping that
you want to use for your number.

+-------------+----------------------------------------------------------------------+
| Rendered as | ``input`` ``text`` field                                             |
+-------------+----------------------------------------------------------------------+
| Options     | - ``rounding_mode``                                                  |
|             | - ``precision``                                                      |
|             | - ``grouping``                                                       |
|             | - ``required``                                                       |
|             | - ``label``                                                          |
|             | - ``read_only``                                                      |
|             | - ``error_bubbling``                                                 |
+-------------+----------------------------------------------------------------------+
| Parent type | ``field``                                                            |
+-------------+----------------------------------------------------------------------+
| Class       | :class:`Symfony\\Component\\Form\\Extension\\Core\\Type\\NumberType` |
+-------------+----------------------------------------------------------------------+

Options
-------

* ``precision`` [type: integer, default: Locale-specific (usually around ``3``)]
    This specifies how many decimals will be allowed until the field rounds
    the submitted value (via ``rounding_mode``). For example, if ``precision``
    is set to ``2``, a submitted value of ``20.123`` will be rounded to,
    for example, ``20.12`` (depending on your ``rounding_mode``).

* ``rounding_mode`` [type: integer, default: ``IntegerToLocalizedStringTransformer::ROUND_DOWN``]
    If a submitted number needs to be rounded (based on the ``precision``
    option), you have several configurable options for that rounding. Each
    option is a constant on the :class:`Symfony\\Component\\Form\\DataTransformer\\IntegerToLocalizedStringTransformer`:
    
    * ``IntegerToLocalizedStringTransformer::ROUND_DOWN``
        Rounding mode to round towards zero.
    * ``IntegerToLocalizedStringTransformer::ROUND_FLOOR``
        Rounding mode to round towards negative infinity.
    * ``IntegerToLocalizedStringTransformer::ROUND_UP``
        Rounding mode to round away from zero.
    * ``IntegerToLocalizedStringTransformer::ROUND_CEILING``
        Rounding mode to round towards positive infinity.
    * ``IntegerToLocalizedStringTransformer::ROUND_HALFDOWN``
        Rounding mode to round towards "nearest neighbor" unless both neighbors
        are equidistant, in which case round down.
    * ``IntegerToLocalizedStringTransformer::ROUND_HALFEVEN``
        Rounding mode to round towards the "nearest neighbor" unless both
    	neighbors are equidistant, in which case, round towards the even
    	neighbor.
    * ``IntegerToLocalizedStringTransformer::ROUND_HALFUP``
        Rounding mode to round towards "nearest neighbor" unless both neighbors
        are equidistant, in which case round up.

.. include:: /reference/forms/types/options/required.rst.inc

.. include:: /reference/forms/types/options/label.rst.inc

.. include:: /reference/forms/types/options/read_only.rst.inc

.. include:: /reference/forms/types/options/error_bubbling.rst.inc
