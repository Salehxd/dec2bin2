def get_rest(dec, pow)
    return dec % (2 ** pow)
end

def convert(dec, bin, pow)
    while dec > 0 
        rest = get_rest(dec, pow)
        if rest > 0
            bin.insert(0, '1')
        else
            bin.insert(0, '0')
        end
        dec -= rest
        pow += 1
    end
    return bin
end

def main
    bin = ""
    pow = 1
    puts "\nInput positive decimal"
    dec = gets.to_i
    binary = convert(dec, bin, pow)
    puts "Your decimal to binary conversion is " + binary
end

main
